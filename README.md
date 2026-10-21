# Coordinate Agent Work

面向 Codex 等支持 SKILL.md 的工具，用于多阶段项目中的主管、实现者和独立验收者协作。

重点：交付后接续、主动上下文检查、冻结输入、风险匹配验证和安全交接。默认可被自动发现；只在多阶段协作场景触发，不要求普通单文件修改也拆成三角色。

## 安装

将 `skills/coordinate-agent-work` 文件夹复制到你的技能目录，例如 Codex 的 `~/.codex/skills/`。已存在同名技能时先比较，不直接覆盖。

在支持的客户端中刷新技能或新建会话后，可显式使用：

```text
使用 $coordinate-agent-work 检查项目当前停点，接收已有交付，继续已授权任务。
```

## 文件

- `skills/coordinate-agent-work/SKILL.md`：精简入口。
- `references/context-check.md`：位于技能目录内，上下文数据解释与交接判断。
- `references/handoff-templates.md`：位于技能目录内，按需任务卡和交接模板。
- `agents/openai.yaml`：位于技能目录内，Codex界面元数据。

## 能力边界

这是指令技能，不是常驻调度服务或自动压缩插件。它不自行监控后台，不安装工具，不创建角色，不扩大写入、消息发送或模型费用授权。

上下文日志字段仅为可选读取方法，须核对版本、会话身份和采样有效性。没有可靠数据时报告未知。Skill不能保证判断质量或效率提升。

不包含真实项目路径、聊天ID、数据库配置、凭据或用户原始文档。

## 方法参考

- [OpenAI：上下文生命周期](https://developers.openai.com/blog/mastering-codex-remote-for-engineering#7-manage-context-before-it-becomes-a-problem)
- [Superpowers：按任务组织协作](https://github.com/obra/superpowers/blob/main/skills/subagent-driven-development/SKILL.md)
- [Anthropic：增量功能闭环](https://github.com/anthropics/claude-quickstarts/blob/main/autonomous-coding/prompts/coding_prompt.md)
- [OpenHands：隔离实例与验证](https://github.com/OpenHands/OpenHands/blob/main/.agents/skills/verify-openhands/SKILL.md)

内容为独立编写的工作流适配，未打包上述项目代码或用户提供的第三方文章。来源链接不表示本包具备它们的工具能力。
