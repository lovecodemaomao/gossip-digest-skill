# Gossip Digest Skill / 聊天关系梳理 Skill

中文说明优先。English version: [README.en.md](README.en.md)

`gossip-digest` 是一个 Codex Skill，用来把混乱的群聊截图、复制聊天记录、网络事件、抽象对话、吃瓜/爆料材料、PDF、Word、PPT 和多文件材料包，整理成简短说明、人物关系图、时间线、争议点、证据边界，以及可选的 Word/PNG 快速传播版本。

它的核心目标不是判断谁对谁错，而是：

> 快速看懂发生了什么、有哪些人、谁和谁是什么关系、哪些内容有材料支持、哪些地方不能确认。

## 主要功能

- 将混乱材料总结成简短、可读的说明。
- 抽取人物、昵称、别名、材料中的身份和立场。
- 在材料明确支持时标注性别；不根据名字、头像或语气猜性别。
- 生成 Mermaid 人物关系图。
- 在需要时整理关键事件时间线。
- 区分材料明确内容、模型推测、争议点和证据不足。
- 默认使用容易记忆的匿名标签，例如 `小黄`、`小红`、`小蓝`、`小绿`。
- 隐藏手机号、身份证号、地址、私人账号、学校班级、工作单位、未成年人身份等敏感信息。
- 用户需要时，可指导生成快速阅读 Word、人物关系图 PNG、一分钟摘要卡 PNG。

## 适合场景

- QQ / 微信 / Discord / Telegram 群聊截图 OCR 后的快速梳理。
- 复制出来的聊天记录或导出的对话文本。
- 多人参与、关系混乱的网络事件。
- 抽象聊天、群内争论、项目或社交沟通复盘。
- 吃瓜、爆料、澄清材料中需要谨慎措辞的内容。
- PPT / PDF / DOCX / TXT / Markdown 材料的结构化阅读。

## 输出模式

- **Quick chat mode / 快速聊天模式**  
  适合 QQ 群截图、普通群聊、抽象对话。输出简介、人物关系图、主要人物、关键点和不确定处。

- **Incident mode / 事件模式**  
  适合多人争议、网络事件、互相回应的材料。输出摘要、关系图、简短时间线、争议点和证据限制。

- **Full dossier mode / 完整材料模式**  
  适合长文档、多文件包、需要 Word/图片产物的场景。输出完整报告、人物表、关系表、时间线、争议分析、隐私说明和可选传播文件。

## 安全和表达风格

这个 Skill 会避免把未经证实的爆料写成事实。推荐使用这类表达：

- “材料显示……”
- “聊天记录中出现……”
- “群聊截图看起来是在讨论……”
- “目前无法确认……”

它不会输出辱骂性标签、人肉信息，或没有证据支持的定罪式判断。

## 安装

把 `gossip-digest` 文件夹复制到 Codex skills 目录。

Windows PowerShell：

```powershell
Copy-Item -Recurse .\gossip-digest $env:USERPROFILE\.codex\skills\
```

macOS / Linux：

```bash
cp -R ./gossip-digest ~/.codex/skills/
```

然后开启新的 Codex 会话，直接点名 `$gossip-digest`，或描述一个匹配任务，例如：

```text
用 gossip-digest 帮我快速梳理这些 QQ 群聊天截图，给我简介和人物关系图。
```

## 仓库结构

```text
gossip-digest/
├── SKILL.md
└── agents/
    └── openai.yaml
```

这个 Skill 故意保持轻量，不内置 OCR、PDF 解析或文档解析脚本。实际使用时，Codex 可以先调用可用工具或其他 Skill 提取文本，再按本 Skill 的流程进行分析。
