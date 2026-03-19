%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#003366', 'edgeLabelBackground':'#ffffff', 'tertiaryColor': '#fff'}}}%%
graph TD
    %% Define styles
    classDef mainTitle fill:#fff,stroke:#003366,stroke-width:2px,font-size:18px,font-weight:bold,color:#003366;
    classDef stepNode fill:#003366,stroke:#333,stroke-width:2px,color:#fff,font-weight:bold,font-size:16px,rx:5,ry:5;
    classDef actionNode fill:#e1f5fe,stroke:#01579b,stroke-width:1px,color:#000,font-size:14px,rx:10,ry:10;
    classDef subActionNode fill:#f0f4c3,stroke:#827717,stroke-width:1px,color:#000,font-size:14px,rx:8,ry:8;
    classDef highlightNode fill:#e8f5e9,stroke:#2e7d32,stroke-width:1px,font-size:14px,rx:10,ry:10,color:#000;
    classDef detailNode fill:#eeeeee,stroke:#616161,stroke-width:1px,font-size:12px,rx:5,ry:5,color:#333;
    classDef resultNode fill:#fff8e1,stroke:#fbc02d,stroke-width:2px,font-weight:bold,color:#000;

    %% Main Title
    Title[解题思路总结 - 四步法]
    class Title mainTitle;

    %% Steps and Main Connections
    Start((Start)) --> Title
    Title --> Step1
    Step1 --> Step2
    Step2 --> Step3
    Step3 --> Step4
    Step4 --> Result
    class Start resultNode;

    %% Step 1 Details
    subgraph S1 [第一步:对标竞品 与 华为优势]
        Step1[精准对标竞品,锚定华为核心优势]
        
        AnalyzeCP[分析竞品致命短板]
        
        CompareN[国际厂商N]
        CPN1[交付周期长: 6-12个月]
        CPN2[不合规: 外资]
        CPN3[全栈缺失/高供应链风险/无生态]
        CompareN --- CPN1 --- CPN2 --- CPN3

        CompareJ[国内厂商J]
        CPJ1[合规不彻底: 核心器件依赖国外]
        CPJ2[技术成熟度低/全栈碎片化]
        CPJ3[服务空白/行业方案缺失]
        CompareJ --- CPJ1 --- CPJ2 --- CPJ3

        AnalyzeCP --> CompareN
        AnalyzeCP --> CompareJ

        ShowADV[展现华为独家优势]
        HW1[超短交付: 15天备货+45天部署]
        HW2[100%全栈国产化: 昇腾+鲲鹏+自研/零合规风险]
        HW3[存算网服全栈统一: 算力利用率85%+]
        HW4[校政企生态赋能: 高校/政企/招商]
        HW5[全周期保障: 电力/散热/人才/5年服务]
        ShowADV --- HW1 --- HW2 --- HW3 --- HW4 --- HW5

        Step1 --> AnalyzeCP
        Step1 --> ShowADV
    end
    class Step1 stepNode;
    class AnalyzeCP actionNode;
    class ShowADV actionNode;
    class CompareN,CompareJ subActionNode;
    class CPN1,CPN2,CPN3,CPJ1,CPJ2,CPJ3 detailNode;
    class HW1,HW2,HW3,HW4,HW5 highlightNode;

    %% Step 2 Details
    subgraph S2 [第二步:算力分配 与 生态布局]
        Step2[S市校政企三位一体算力分配]
        
        DistributeG[政府端: 35%, 70P]
        G1[政务池 30P / 合规池 25P / 公共池 15P]
        GAdv[优势: 合规领先、需求稳定,首年消化35%]
        DistributeG --- G1 --- GAdv

        DistributeU[高校端: 20%, 40P]
        U1[科研池 15P / 实训池 20P / 创新池 5P]
        UAdv[优势: 人才就业、联合科研申报]
        DistributeU --- U1 --- UAdv

        DistributeE[企业端: 45%, 90P]
        E1[高端训练池 35P / 普惠池 40P / 定制池 15P]
        EAdv[优势: 联合招商、行业方案打包]
        DistributeE --- E1 --- EAdv

        Step2 --> DistributeG
        Step2 --> DistributeU
        Step2 --> DistributeE
    end
    class Step2 stepNode;
    class DistributeG,DistributeU,DistributeE actionNode;
    class G1,U1,E1 detailNode;
    class GAdv,UAdv,EAdv highlightNode;

    %% Step 3 Details
    subgraph S3 [第三步:风险管控]
        Step3[全周期基建风险管控]
        
        CtrlP[电力规划]
        P1[200P当下: 现有机房适配]
        P2[100P未来: 预留专线接口, PUE 1.1]
        CtrlP --- P1 --- P2

        CtrlC[散热与水利]
        C1[200P当下: 风冷优化]
        C2[1000P未来: 冷板式液冷 PUE 1.04, 余热回收]
        CtrlC --- C1 --- C2

        CtrlT[人才配套]
        T1[创造岗位: 30(当下) / 200+(未来)]
        T2[留存政策: 公寓 + 实训 + 就业]
        CtrlT --- T1 --- T2

        Step3 --> CtrlP
        Step3 --> CtrlC
        Step3 --> CtrlT
    end
    class Step3 stepNode;
    class CtrlP,CtrlC,CtrlT actionNode;
    class P1,P2,C1,C2,T1,T2 detailNode;

    %% Step 4 Details
    subgraph S4 [第四步:落地与准备]
        Step4[方案落地与准备工作]
        
        WorkR[调研与锁定]
        WR1[竞品短板锁定]
        WR2[S市本地需求调研]
        WorkR --- WR1 --- WR2

        WorkP[硬件方案适配]
        WP1[三套方案保底/旗舰/生态]
        WP2[适配1.36亿预算]
        WorkP --- WP1 --- WP2

        WorkB[商业与风险]
        WB1[商业测算: 18个月回本]
        WB2[全流程风险预案]
        WorkB --- WB1 --- WB2

        Step4 --> WorkR
        Step4 --> WorkP
        Step4 --> WorkB
    end
    class Step4 stepNode;
    class WorkR,WorkP,WorkB actionNode;
    class WR1,WR2,WP1,WP2,WB1,WB2 detailNode;

    %% Core Results
    subgraph SR [核心结果]
        Result(核心关键词:\n昇腾唯一技术路线\n全栈国产化\n校政企生态闭环\n基建风险管控\n商业正循环)
    end
    class Result resultNode;

    %% Vertical alignment for result nodes
    ShowADV -.-> Result
    DistributeE -.-> Result
    CtrlT -.-> Result
    WorkB -.-> Result  
