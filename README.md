好的，这是为您项目编写的 README.md 文档：

```markdown
# Crazy Party - 趣味多人互动游戏集合

一个基于 uni-app 开发的跨平台移动应用，集成了多种有趣的派对游戏模式，包括卡牌游戏、幸运转盘等，适合朋友聚会、情侣互动和破冰活动。

## 🎮 项目特色

- **多模式选择**: 提供派对模式、情侣模式、破冰模式等多种场景
- **卡牌游戏集合**: 包含6种不同的卡牌互动游戏
- **幸运转盘**: 有趣的随机抽选功能，增加聚会趣味性
- **跨平台支持**: 使用 uni-app 开发，支持 iOS、Android、微信小程序等多端

## 📱 功能特性

### 游戏模式
- **卡牌游戏1-6**: 六种不同主题的卡牌互动游戏
- **聚会模式**: 适合朋友聚会的轻松游戏
- **情侣模式**: 专为情侣设计的亲密互动游戏  
- **破冰模式**: 帮助陌生人快速熟悉的热场游戏

### 技术特性
- Vue.js 框架开发
- 响应式UI设计，支持多种屏幕尺寸
- 内置丰富的工具类样式系统
- 支持第三方API集成（OpenAI、Axios）

## 🚀 快速开始

### 环境要求
- Node.js (推荐 14.x 或更高版本)
- HBuilderX (uni-app 开发工具)
- 微信开发者工具 (如需小程序端调试)

### 安装依赖
```bash
npm install
```

### 开发运行
```bash
# 运行到微信小程序
npm run dev:mp-weixin

# 运行到H5
npm run dev:h5

# 运行到App
npm run dev:app
```

### 生产构建
```bash
# 构建微信小程序
npm run build:mp-weixin

# 构建H5
npm run build:h5

# 构建App  
npm run build:app
```

## 📁 项目结构

```
uniapp/
├── pages/                 # 页面目录
│   ├── page1/            # 卡牌游戏主页面
│   ├── page1_1-1_6/      # 6种卡牌游戏子页面
│   ├── page2/mode        # 模式选择页面
│   └── lottery_wheel1-3  # 三种幸运转盘页面
├── App.vue               # 应用入口组件
├── main.js               # 应用入口文件
├── manifest.json         # 应用配置文件
├── pages.json           # 页面路由配置
├── uni.scss             # 全局样式变量
└── package.json         # 项目依赖配置
```

## 🎨 样式系统

项目内置了丰富的工具类样式：
- 弹性布局工具类 (`flex-row`, `flex-col`, `justify-*`, `items-*`)
- 间距工具类 (`ml-*`, `mt-*` 从 2 到 100)
- 定位工具类 (`relative`, `self-*`)
- 响应式设计，使用 rpx 单位

## 🔧 技术栈

- **前端框架**: Vue.js + uni-app
- **构建工具**: Webpack (uni-app 内置)
- **HTTP客户端**: Axios
- **AI集成**: OpenAI API
- **样式预处理**: SCSS

## 📦 依赖说明

主要依赖包：
- `axios`: ^1.11.0 - HTTP 请求库
- `openai`: ^5.12.2 - OpenAI API 客户端

## 🌐 多端支持

本项目支持编译到以下平台：
- 📱 iOS & Android App
- 💬 微信小程序
- 🎯 支付宝小程序
- 🔍 百度小程序
- 📺 头条小程序
- 🌐 H5 网页

## 🔐 权限配置

Android 权限包括：
- 相机访问
- 网络状态访问
- 振动功能
- 读取手机状态
- 闪光灯控制等

## 🤝 贡献指南

1. Fork 本项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 📄 许可证

本项目基于 MIT 许可证开源 - 查看 [LICENSE](LICENSE) 文件了解详情

## 🆘 常见问题

### Q: 如何添加新的游戏模式？
A: 在 `pages.json` 中添加新的页面路由，然后在 `pages` 目录下创建对应的页面组件。

### Q: 如何修改主题颜色？
A: 编辑 `uni.scss` 文件中的颜色变量。

### Q: 如何集成新的第三方API？
A: 在 `package.json` 中添加依赖，然后在需要的页面中引入使用。

## 📞 联系方式

如有问题或建议，请通过以下方式联系：
- 邮箱: 1581539362@qq.com
- GitHub: [YYPumpkin](https://github.com/YYPumpkin)

---

**Enjoy your party! 🎉**
```

这个 README.md 文档包含了项目的完整介绍，包括功能特性、技术栈、安装指南、项目结构等信息。您可以根据实际需求进一步修改和完善。
