# codex-prompt-pack

一套给 Codex（桌面端 / CLI）用的提示词，主要用来防 GPT 模型偷懒，也减少它在授权范围内因过度谨慎而反复确认或提前停手的情况。

## 文件

- [AGENTS.md](AGENTS.md)：全局规则
- [PLANS.md](PLANS.md)：复杂任务的执行计划（ExecPlan）模板
- [PROMPTS.md](PROMPTS.md)：7 套分段指令（完整实施、只读调研、写计划、分步执行、独立验收、修 Review、复盘交接）

## 安装

把 `AGENTS.md`、`PLANS.md`、`PROMPTS.md` 放到 Codex 主目录（加载规则见 [Codex 文档](https://learn.chatgpt.com/docs/agent-configuration/agents-md)）：

- macOS / Linux / WSL：`~/.codex`
- Windows：`%USERPROFILE%\.codex`
- 配了 `CODEX_HOME` 环境变量的话，以它为准

目录里原本有 `AGENTS.md` 或非空的 `AGENTS.override.md`，记得先备份再合并。

## 使用

默认中文回复，想换语言改一下 `AGENTS.md` 开头就行。
