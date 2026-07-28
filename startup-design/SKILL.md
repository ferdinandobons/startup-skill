---
name: startup-design
description: 把创业想法从原始概念推进到可验证方案，覆盖预检、访谈、市场研究、商业模式、品牌、产品、财务与验证实验。适用于“我有个创业想法”“帮我验证项目”“商业计划”“市场规模”“商业模式”“进入中国市场”等请求，也支持根据 PROGRESS.md 续跑。
---

# 创业设计

预检 → 需求访谈 → 方案发散 → 四轮研究 → 研究闸门 → 客户发现 → 战略 → 品牌 → 产品 → 财务 → 验证

默认全程输出简体中文，以可追溯证据服务中国市场决策。

## 中国市场通用规则

- 默认使用简体中文提问、检索、分析和交付；用户明确要求其他语言时再切换。
- 金额默认以人民币（CNY）表示，同时写清含税/未税、月付/年付及数据日期。
- 先确认目标区域是中国大陆、港澳台还是出海市场；不得把“中文市场”等同于中国大陆。
- 检索优先级：政府与监管部门、国家统计局/地方统计局、交易所公告、企业官网/公众号、主流电商与应用商店，再到可信行业报告和社区内容。
- 社区信号可来自微信、知乎、小红书、抖音、B站、微博、脉脉、即刻、少数派及垂直论坛；受登录限制时说明缺口，不伪造浏览结果。
- 涉及个人信息、数据跨境、生成式 AI、算法推荐、广告、电商、金融、医疗、教育、地图或出版时，只做风险识别并建议咨询中国执业专业人士，不输出无依据的“合规确认”。
- 明确区分事实、推断、假设和建议；事实附可访问链接、发布日期/访问日期，关键结论至少两类独立来源交叉验证。
- 禁止把媒体转载链当作多个独立来源，禁止虚构市场规模、融资、客户数、价格、备案或牌照。
- 免费工具优先：具备免费额度的通义千问/Qwen、DeepSeek、豆包、Kimi、智谱清言、Gemini CLI，或通过 Ollama 本地运行 Qwen/DeepSeek 等开源模型。免费政策会变化，使用前由用户确认；不得要求特定付费模型或订阅。
- 工具不可用时进入“知识库模式”：只产出假设、检索清单和待验证项，不把模型记忆包装成实时调研。


## 执行流程

### 0. 续跑与预检
先查找 `PROGRESS.md`。存在则说明已完成阶段并从断点继续；不存在则进行 2—3 组快速检索：主导方案、同类失败案例、监管/牌照硬约束。预检只提示风险，不替用户下结论。

### 1. 需求访谈
每轮询问 3—5 个问题，覆盖用户、痛点、创始团队、地域、商业目标、资源与约束。创建 `{项目名}/PROGRESS.md`、`00-intake/brief.md` 和 `00-intake/preflight.md`。

### 2. 方案发散
提出 5—8 个有实质差异的方案，从痛点强度、付费方、渠道、监管、冷启动和创始人优势评分；不只改名字或功能。

### 3. 市场研究
按顺序完成四轮：①市场与监管；②竞品与价格；③客户需求与中文社区信号；④中国渠道与单位经济。轮内可并行，轮间必须等待。研究前按 `research-scaling.md` 评估轻量/标准/深度。保存原始证据和综合结论。

### 3.5 研究闸门与 3.7 客户发现
展示机会、反证、关键未知和继续/调整/停止建议。用户确认后，至少完成 5 次真实访谈或把未访谈标为关键风险；AI 模拟访谈只能用于练习，不能作为客户证据。

### 4—8. 落地设计
依次交付战略、品牌、产品、财务和验证。财务先用假设区间，再用真实数据更新；中国税费、平台抽佣、支付费率、获客成本与回款周期必须单列。最后给 30 天实验计划与停止条件。

### 快速模式
保留预检、简化访谈、市场与竞品两轮研究、研究闸门、至少 3 次客户访谈、精益画布、收入模型和前三项实验；不得跳过合规风险与证据标注。

## 交付目录

- `00-intake/`：需求简报、预检、访谈
- `01-discovery/`：市场、竞品、客户、渠道及原始证据
- `02-strategy/`：精益画布、定位、商业模式、进入市场策略
- `03-brand/`：使命、愿景、中文语气与禁用表达
- `04-product/`：MVP、功能优先级、用户旅程
- `05-financial/`：收入、成本、现金流与情景预测
- `06-validation/`：实验、风险、评分表和 30 天计划

## 质量闸门

- 每个关键数字都有来源、口径、日期和置信度；找不到就写“待验证”。
- 将结果分为“已验证事实 / 有依据推断 / 创始人假设 / 建议动作”。
- 发现关键矛盾、监管硬风险或证据不足时暂停，向用户展示问题与可选路径。
- 每阶段完成后更新 `PROGRESS.md`，记录研究模式、深度、已完成文件和下一步。
- 只读取当前阶段需要的参考资料，控制上下文和免费模型用量。

## 参考资料

- `startup-design/references/customer-interview.md`
- `startup-design/references/frameworks.md`
- `startup-design/references/honesty-protocol.md`
- `startup-design/references/industry-benchmarks.md`
- `startup-design/references/intake-questions.md`
- `startup-design/references/output-guidelines.md`
- `startup-design/references/output-specs.md`
- `startup-design/references/research-principles.md`
- `startup-design/references/research-scaling.md`
- `startup-design/references/research-synthesis.md`
- `startup-design/references/research-wave-1-market.md`
- `startup-design/references/research-wave-2-competitors.md`
- `startup-design/references/research-wave-3-customers.md`
- `startup-design/references/research-wave-4-distribution.md`
- `startup-design/references/verification-agent.md`
