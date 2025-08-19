<template>
  <div class="lottery-container">
    <!-- 转盘部分 -->
    <h1 class="game-title">真心话大冒险转盘</h1>
    <div class="wheel-container">
      <img 
        class="wheel-image" 
        src="static/6.jpg" 
        alt="惩罚转盘"
        :style="{ transform: `rotate(${currentAngle}deg)` }"
      >
      
      <button 
        class="start-btn" 
        @click="startLottery" 
        :disabled="isRotating"
      >
        {{ isRotating ? '选择中...' : '开始挑战' }}
      </button>
    </div>

    <!-- 中奖弹窗 -->
    <div v-if="showDialog" class="dialog-overlay">
      <div class="dialog-content">
        <h3>你的挑战是：</h3>
        <p class="prize-result">{{ result }}</p>
        <button class="dialog-btn" @click="closeDialog">接受惩罚</button>
      </div>
    </div>
  </div>
</template>

<script>
import OpenAI from 'openai';

export default {
  name: 'TruthOrDareWheel',
  data() {
    return {
      currentAngle: 0,
      isRotating: false,
      result: null,
      showDialog: false,
      currentDifficulty: null,
      difficultyLevels: [
        "非常简单", "简单", "中等", "稍难",
        "困难", "非常困难", "极度困难", "地狱难度"
      ],
      prizeSections: Array(8).fill().map((_, i) => ({
        startAngle: i * 45,
        endAngle: (i + 1) * 45,
        difficulty: i + 1
      })),
      conversationHistory: [
        { 
          role: "system", 
          content: `你是一个朋友聚会游戏惩罚生成器，专门生成适合朋友的有趣惩罚任务。
要求：
1. 每次生成100个不重复的惩罚
2. 从中随机选择第7个作为回答
3. 内容可以有一点小尺度但不过分
4. 每次回答必须完全不同
5. 直接返回惩罚内容，不要解释，不超过17个字` 
        }
      ],
      usedPunishments: new Set(), // 用于记录已使用的惩罚
      openai: null
    }
  },
  created() {
    this.initializeOpenAI();
  },
  methods: {
    initializeOpenAI() {
      this.openai = new OpenAI({
        baseURL: 'https://api.deepseek.com',
        apiKey: 'sk-5160540cc40548f2831bbae292beed37', // 请替换为有效API密钥
        dangerouslyAllowBrowser: true
      });
    },

    async generatePunishment(difficulty) {
      // 添加用户请求到历史记录
      const userPrompt = `生成一个难度为${this.difficultyLevels[difficulty-1]}的聚会大冒险惩罚，确保与之前完全不同`;
      this.conversationHistory.push({ role: "user", content: userPrompt });

      try {
        let punishment = "";
        let attempts = 0;
        const maxAttempts = 3; // 最大尝试次数
        
        // 确保生成的惩罚不重复
        do {
          const completion = await this.openai.chat.completions.create({
            model: "deepseek-chat",
            messages: this.conversationHistory,
            temperature: 0.9, // 提高创造性
            max_tokens: 30
          });

          punishment = completion.choices[0]?.message?.content?.trim() || "";
          
          // 清理可能的标点符号和空白
          punishment = punishment.replace(/^["']|["']$/g, '').trim();
          
          attempts++;
          if (attempts >= maxAttempts) break;
          
        } while (this.usedPunishments.has(punishment) || punishment.length > 17 || !punishment);

        // 如果仍然重复或无效，使用备用
        if (!punishment || this.usedPunishments.has(punishment)) {
          punishment = this.getUniqueBackupPunishment(difficulty);
        }

        // 记录已使用的惩罚
        this.usedPunishments.add(punishment);
        this.conversationHistory.push({ role: "assistant", content: punishment });

        return punishment;
      } catch (error) {
        console.error("API调用失败:", error);
        return this.getUniqueBackupPunishment(difficulty);
      }
    },

    getUniqueBackupPunishment(difficulty) {
      const backups = {
        1: ["轻咬对方耳朵说情话", "对视30秒不许笑", "用奶音读一段话"],
        2: ["公主抱对方10秒钟", "模仿对方习惯动作", "用领带蒙眼喂水果"],
        3: ["隔纸巾亲吻10秒", "帮对方按摩1分钟", "模仿动物求偶叫声"],
        4: ["解开对方一颗纽扣", "用嘴传递纸条", "模仿床戏台词"],
        5: ["隔着保鲜膜接吻", "帮对方脱外套", "模仿情侣吵架和好"],
        6: ["用口红画对方脸", "表演壁咚场景", "模仿求婚场景"],
        7: ["咬住对方衣领不放", "模仿洗澡动作", "表演被强吻反应"],
        8: ["模仿洞房花烛夜", "用身体写对方名字", "表演怀孕分娩"]
      };
      
      const available = backups[difficulty].filter(p => !this.usedPunishments.has(p));
      return available.length > 0 
        ? available[Math.floor(Math.random() * available.length)]
        : "创造一个新惩罚";
    },

    async startLottery() {
      if (this.isRotating || !this.openai) return;
      
      this.isRotating = true;
      this.result = null;
      this.showDialog = false;
      
      // 随机选择分区
      const targetIndex = Math.floor(Math.random() * this.prizeSections.length);
      const targetSection = this.prizeSections[targetIndex];
      const targetAngle = Math.random() * (targetSection.endAngle - targetSection.startAngle) + targetSection.startAngle;
      
      // 开始旋转动画
      this.animateWheel(targetAngle, async () => {
        // 动画结束后生成惩罚内容
        this.result = await this.generatePunishment(targetSection.difficulty);
        this.currentDifficulty = this.difficultyLevels[targetSection.difficulty-1];
        this.showDialog = true;
        this.isRotating = false;
      });
    },

    animateWheel(targetAngle, callback) {
      const startAngle = this.currentAngle;
      const endAngle = startAngle + 720 + (360 - targetAngle);
      const duration = 2000;
      const startTime = performance.now();
      
      const animate = (currentTime) => {
        const elapsed = currentTime - startTime;
        const progress = Math.min(elapsed / duration, 1);
        const easing = progress < 0.8 ? 
          progress / 0.8 : 
          1 - Math.pow((progress - 0.8) / 0.2, 2);
        
        this.currentAngle = startAngle + (endAngle - startAngle) * easing;
        
        if (progress < 1) {
          requestAnimationFrame(animate);
        } else {
          this.currentAngle = endAngle % 360;
          if (callback) callback();
        }
      };
      
      requestAnimationFrame(animate);
    },

    closeDialog() {
      this.showDialog = false;
    }
  }
}
</script>

<style scoped>
/* 修改按钮和弹窗颜色为更刺激的粉色系 */
.start-btn {
  background-color: #ffcbdd;
  color: #ffffff;
  /* 其他样式保持不变 */
}

.dialog-btn {
  background-color: #ffcbdd;
  color: #ffffff;
  margin-top: 20px;
  /* 其他样式保持不变 */
}

/* 其余样式保持原样 */
.lottery-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px;
  position: relative;
  margin-top: -10px;
}

.game-title {
  position: absolute;
  top: 80px;
  left: 0;
  right: 0;
  text-align: center;
  font-size: 36px;
  font-weight: bold;
  color: #000000;
  margin: 0;
  z-index: 1;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
}

.wheel-container {
  position: relative;
  width: 300px;
  height: 300px;
  margin-top: 150px;
  margin-bottom: 20px;
}

.wheel-image {
  width: 100%;
  height: 100%;
  transition: transform 0.1s linear;
  transform-origin: center center;
  border-radius: 50%;
}
.prize-result {
  padding: 12px;
  border-radius: 8px;
  display: inline-block;
  font-size: 18px;
  margin-bottom: -25px;
}

/* 其他原有样式... */
</style>