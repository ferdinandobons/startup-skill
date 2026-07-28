# AGENTS.md

本仓库包含四个面向中国市场的通用 Agent Skills：`startup-design`、`startup-competitors`、`startup-positioning` 和 `startup-pitch`。

## 修改规则

- 技能目录名必须与 `SKILL.md` frontmatter 的 `name` 一致，使用小写英文和连字符。
- `description` 为 1—1024 个字符，包含清晰的中文触发场景；`SKILL.md` 不超过 500 行。
- 默认使用简体中文；中国市场数据必须注明来源、日期、地域、币种和统计口径。
- 阶段细节放入 `references/`，研究轮次文件使用 `research-wave-N-` 前缀并按需加载。
- 不绑定特定商业模型，不要求付费订阅或 API Key；优先兼容通用 Agent Skills、免费额度模型和 Ollama 本地模型。
- 搜索不可用时进入知识库模式，明确标记假设和待验证项，不伪造实时来源。
- 四个技能的研究轮次必须顺序执行；轮内是否并行由当前 Agent 环境决定。
- 修改后检查 YAML frontmatter、相对路径、文件行数和平台耦合词。

## Git

提交信息使用 Conventional Commits：`feat:`、`fix:`、`docs:` 或 `test:`。分支使用 `feature/`、`fix/` 或 `docs/` 前缀。
