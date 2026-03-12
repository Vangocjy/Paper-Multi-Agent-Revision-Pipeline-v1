# Paper-Multi-Agent-Revision-Pipeline-v1
This project solely supports the use of openclaw to achieve language style alignment and polishing, as well as format typesetting for target journal papers in desired formats (including journal articles, conference papers, theses/dissertations, etc.). Users need to independently judge whether the final results meet the required standards.
## 1. 项目介绍

这个项目用于把论文初稿（`paper.tex`）通过多 Agent 协同方式，迭代修订为“**reviewer 友好 + 格式规范 **”版本。
如下图演示的是，将word中文论文初稿通过Pandoc转化后得到letax版本，然后通过本项目多agent迭代后得到的最终结果图（因为隐私等问题，这边进行了加噪处理，大家见谅）。
![result](result.png)



本项目仅支持通过openclaw实现对于目标格式（包括期刊/会议/毕业论文等）进行目标期刊论文的语言风格对齐润色以及格式排版，最终效果是否达标需要自己进行判断。

## 2. 目录结构

```text
├─ workspace-orchestrator/ # 调度与流程控制
├─ workspace-writer/ # 内容改写 agent
├─ workspace-latex/ # LaTeX/图表格式 agent
├─ workspace-reviewer/ # reviewer 评审 agent
└─ workspace-shared/ # agent交互共享工作空间
	├─ paper.tex # 论文原稿
	├─ revision_packets/
	├─ latex_packets/
	├─ review_packets/
	└─ final/
```

## 3. Agent 分工

- **writer**：英文重写、逻辑收敛、证据链与结论措辞修订
- **latex**：表格可读性优化、图片接入、交叉引用/编译闭环
- **reviewer**：按高/中/低优先级给出 action list 和是否可投判定
- **orchestrator**：统一调度、追踪进度、汇总结果

## 4. 项目部署

### 4.1 OpenClaw安装

openclaw安装教程参考 https://openclaws.io/ 或者参考知网这个博主 https://zhuanlan.zhihu.com/p/2000705640474100436 （感谢博主提供教程）

这边使用的是windows powershell（管理员模式）

```bash
iwr -useb https://openclaw.ai/install.ps1 | iex
```

官网承诺：自动安装 [Node.js](https://zhida.zhihu.com/search?content_id=269795282&content_type=Article&match_order=1&q=Node.js&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3NzMzOTI1NTAsInEiOiJOb2RlLmpzIiwiemhpZGFfc291cmNlIjoiZW50aXR5IiwiY29udGVudF9pZCI6MjY5Nzk1MjgyLCJjb250ZW50X3R5cGUiOiJBcnRpY2xlIiwibWF0Y2hfb3JkZXIiOjEsInpkX3Rva2VuIjpudWxsfQ.xATF7ST4vh3cjCEtqeLMrqch4_6LdpOuSpDIuAw1I8k&zhida_source=entity) 和所有依赖，支持 macOS / Windows / Linux

接下来是选择对应的AI模型（跳过也没问题，后续去找openclaw即可），本地部署如果算力不支持最好使用API以及tokens使用的问题，（如果算力有限，可以查找相关教程进行精细化的token管理，这边我用的codex包月的api，所以没做）

后面是 hook（可选）等个性化设置以及API设置 按照个人喜欢吧

### 4.2  项目设置

1. 语言风格学习设置：我这边默认设置的期刊是xxxx，先检索了十几篇xxxx期刊（pdf）放在了`workspace-reviewer\journal_samples`路径下，`agent-reviewer`会在第一轮迭代前对于这些期刊进行学习总结。

2. 期刊letax格式风格设置：在对应期刊下载模板文件保存在`workspace-reviewer\IEEE-TJ-color-latex-template`作为reviewer的对照模板，以及`workspace-latex\LaTex_Template\IEEE-TJ-color-latex-template`作为`latex-agent`的对齐对象

3. `agent`的风格以及功能设置，可以通过修改对应`AGENTS.md`以及`SOUL.md`，例如，我将reviewer设置为 xxx领域的专家，以及严格的审稿人等等风格设置，这个可以把需求发给AI让他帮你按照你的领域去重写，然后修改对应文件。

4. `agent`注册:

   ```bash
   openclaw agents add orchestrator --workspace "PATHTOPROJECT\workspace-orchestrator" 
   openclaw agents add writer --workspace "PATHTOPROJECTw\workspace-writer" 
   openclaw agents add reviewer --workspace "PATHTOPROJECT\workspace-reviewer" 
   openclaw agents add latex --workspace "PATHTOPROJECT\workspace-latex" 
   ```

5. 最后是openclaw启动项目设置：一般存放在**`C:\Users\UserName\.openclaw\openclaw.json`**主要修改如下字段，指向工程路径，以及配置文件,并且设置orchestrator agent为"default": true。

```json
    "list": [
      {
        "id": "main",
        "name": "main",
        "workspace": "PATHTOPROJECT\\openclaw",
        "agentDir": "C:\\Users\\USERNAME\\.openclaw\\agents\\main\\agent"
      },
      {
        "id": "orchestrator",
        "default": true,
        "name": "orchestrator",
        "workspace": "PATHTOPROJECT\\workspace-orchestrator",
        "agentDir": "C:\\Users\\USERNAME\\.openclaw\\agents\\orchestrator\\agent",
        "subagents": {
          "allowAgents": [
            "writer",
            "reviewer",
            "latex"
          ]
        }
      },
      {
        "id": "writer",
        "name": "writer",
        "workspace": "PATHTOPROJECT\\workspace-writer",
        "agentDir": "C:\\Users\\USERNAME\\.openclaw\\agents\\writer\\agent",
        "subagents": {
          "allowAgents": []
        }
      },
      {
        "id": "reviewer",
        "name": "reviewer",
        "workspace": "PATHTOPROJECT\\workspace-reviewer",
        "agentDir": "C:\\Users\\USERNAME\\.openclaw\\agents\\reviewer\\agent",
        "subagents": {
          "allowAgents": []
        }
      },
      {
        "id": "latex",
        "name": "latex",
        "workspace": "PATHTOPROJECT\\workspace-latex",
        "agentDir": "C:\\Users\\USERNAME\\.openclaw\\agents\\latex\\agent",
        "subagents": {
          "allowAgents": []
        }
      }
    ]
  },

```

### 5. 项目资源准备

1. 初稿放入：

```text
PATHTOPROJECT\workspace-shared\paper.tex
```

2. 期刊样本（reviewer 学风格）放入：

```text
PATHTOPROJECT\workspace-reviewer\journal_samples\
```

3. 目标模板放入：

```text
PATHTOPROJECT\workspace-reviewer\IEEE-TJ-color-latex-template\
PATHTOPROJECT\workspace-latex\LaTex_Template\IEEE-TJ-color-latex-template\
# 这个命名的话如有修改，通过修改对应agent的AGENT.md以及SOUL.md进行修改
```

4. 图片原始资源放入（你当前用这个）：

```text
PATHTOPROJECT\workspace-latex\figures\raw\
```

### 6. 项目启动

### 1) 启动/确认 Gateway

```powershell
openclaw gateway status
```

如果没启动：

```powershell
openclaw gateway start
```

### 2) 检查系统状态

```powershell
openclaw status
```

### 3) 打开控制台页面

浏览器打开（本机）：

```text
http://127.0.0.1:18789/
```

### 4) 在聊天框给 orchestrator 下达任务

- “从第一轮开始，paper.tex 在 workspace-shared，按 writer→latex→reviewer 迭代，输出可投版本，并持续汇报每个 agent 产出文件。”
- 如果几次迭代结果仍然不满意 可以直接在聊天框向orchestrator提出相应需求，orchestrator可以直接修改对应文件

## 7. 最终质量门槛（建议）

提交前至少满足：

- 语言一致（英文稿无中文残留）
- 图像引用完整（缺图=0）
- 编译通过（fatal error=0，undefined ref=0）
- 表格可读性可接受（无严重拥挤）
- reviewer 最终判定达到 Accept 或可接受 Minor

------

## 8. 安全性设置（Security Configuration）

由于该项目涉及 **API Key、论文内容和本地文件系统访问**，建议进行以下安全配置：

------

### 1）限制 Agent 文件权限

建议仅允许 agent 访问以下目录：

```
workspace-shared
workspace-writer
workspace-reviewer
workspace-latex
```

避免 agent 访问：

- 用户主目录
- 系统文件
- 私有数据目录

------

### 2）敏感信息保护

请不要在论文中包含：

- 未公开数据
- 专利未公开内容
- 商业机密
- 个人隐私信息

如果使用 **云端模型 API**，论文内容可能会被：

- 模型日志记录
- API 服务处理

请自行评估风险。

------

### 3）本地运行建议

如果论文涉及敏感数据，建议：

- 使用 **本地模型**
- 或 **私有 API 服务**

避免将数据上传到第三方平台。

------

## 9. 免责声明（Disclaimer）

本项目仅用于 **提升论文写作与排版效率的工程化工具链**。

使用本项目时，请注意：

1. 本工具 **不保证论文质量或审稿结果**
2. 本工具 **不能替代作者的学术判断**
3. AI 生成内容可能存在：
   - 事实错误
   - 引用不准确
   - 表达不严谨
4. 最终论文内容与学术责任 **完全由作者本人承担**

作者在投稿前应：

- 仔细审查所有修改
- 确认引用准确
- 确认数据真实
- 确认符合目标期刊规范

使用本项目即表示：

**用户理解并接受上述风险。**

------

# 10. 致谢

感谢：

- OpenClaw 社区
- 相关教程作者
- AI 工具生态

提供的实践经验和技术支持。


