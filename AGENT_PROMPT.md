# Agent 任务执行提示词：全量提供商免费资源与编程订阅检索

> 📅 创建时间：2026-06-08
> 📂 所属项目：FreeLLM-API-KeyHub
> 🎯 任务目标：基于 `LLM_API_Providers_All.md`（131家提供商），逐一检索免费额度与编程订阅信息，输出新的 `README.md`

---

## 一、任务总览

你是一个专业的大模型产业情报检索 Agent。你的任务是：

1. 读取 `LLM_API_Providers_All.md` 中的全部 **131 家**大模型 API 服务提供商
2. **逐一**对每家提供商执行多关键词网页搜索
3. **必须访问官方网页**核实搜索到的信息（定价页、开发者文档、活动页面等）
4. 提取两类信息：
   - **Part 1 信息**：注册送 Token、代金券、免费额度、永久免费层、邀请奖励、学生福利、限时活动等
   - **Part 2 信息**：编程套餐 / Coding Plan / 包月订阅 / 编码套餐 / Developer Plan 等
5. 按照指定格式输出最终的 `README.md`

**核心原则：宁可多搜不可漏搜，必须访问确切网页核实，不可仅凭搜索摘要臆断。**

---

## 二、检索方法论（每家提供商必须执行的步骤）

### 步骤 1：多关键词网页搜索

对每家提供商，**必须**使用以下关键词组合进行搜索。将 `{name}` 替换为提供商的中文名、英文名、产品名（如有多个名称，分别搜索）。

#### 免费额度检索（Part 1）：

```
搜索组 A（中文）：
  1. "{name} 免费额度 API"
  2. "{name} 注册送 token 代金券"
  3. "{name} 新用户福利 免费"
  4. "{name} 学生优惠 教育"
  5. "{name} 邀请奖励 推荐"

搜索组 B（英文）：
  6. "{name} free tier API pricing"
  7. "{name} free credits sign up"
  8. "{name} student discount developer"
```

#### 编程套餐检索（Part 2）：

```
搜索组 C（中英混合）：
  9.  "{name} coding plan 编程套餐"
  10. "{name} 包月 订阅 编码"
  11. "{name} programming subscription plan"
  12. "{name} developer plan monthly"
```

**要求**：
- 每家提供商**至少执行 4 组搜索**（从上述 12 组中根据提供商属性选择最相关的组合）
- 国内提供商侧重搜索组 A + C
- 国外提供商侧重搜索组 B + C
- 如果某组搜索结果为空，尝试更换关键词组合或使用提供商的产品品牌名搜索

### 步骤 2：访问官方网页核实

**搜索到相关信息后，必须访问以下页面确认**：

```
必访页面清单：
  1. 官方定价页（Pricing Page）—— 通常为 {官网}/pricing 或 {控制台}/billing
  2. 开发者文档首页 —— 查看"Getting Started"中是否提到免费额度
  3. 新用户活动/促销页面 —— 通常在首页 Banner 或"活动中心"
  4. API 控制台/Dashboard —— 查看是否有免费 Tier 说明
  5. 编程套餐专页 —— 如果有 Coding Plan，通常有独立页面
```

### 步骤 3：提取并记录信息

对每家提供商，按以下字段提取信息。如果确实查不到，填写"未查到"：

```
提取字段清单（Part 1）：
  - 平台名称：官方中英文名称 + 平台URL
  - 注册福利：具体赠送内容（多少 Token / 多少元代金券 / 什么免费模型）
  - 有效期：永久 / X天 / X个月 / 限时（截止日期）
  - 邀请/拉新奖励：有无推荐计划，具体奖励内容
  - 学生福利：有无教育/学生优惠，具体内容
  - 前置条件：注册要求（邮箱/手机/实名认证/信用卡等）
  - 备注：支持的模型、特色功能、限速信息等

提取字段清单（Part 2）：
  - 平台名称：官方中英文名称 + 编程套餐URL
  - 套餐档位与价格：每个档位的名称、月费、季费、年费
  - 支持模型：可使用的模型列表
  - 调用限制：各档位的频率/次数/Token限制
  - 首月优惠：有无首月折扣，具体价格
  - 兼容工具：支持的IDE和开发工具（Claude Code、Cursor、Cline等）
  - 备注：其他特色信息
```

### 步骤 4：分类判定

根据检索结果，对每家提供商做出分类判定：

```
判定规则：

【收录至 Part 1（白嫖指南）】满足以下任一条件：
  ✅ 有明确的免费注册赠送（Token / 代金券 / 积分 / 免费额度）
  ✅ 有永久免费层（Free Tier），无需付费即可持续使用
  ✅ 有正在进行的限时免费活动
  ✅ 有实质性的学生/教育/初创企业优惠
  ✅ 有永久免费的模型可调用
  ❌ 仅有"14天免费试用"且试用后必须付费 → 一般不收录，除非试用额度非常慷慨
  ❌ 纯企业级ToB服务，无个人开发者免费路径 → 不收录

【收录至 Part 2（编程订阅计划）】满足以下全部条件：
  ✅ 有明确的面向 AI 编程/Coding 场景的包月或订阅计划
  ✅ 套餐名称包含 Coding / 编程 / 编码 / Programming / Developer Plan 等关键词
  ✅ 提供固定月费 + 大量 API 调用额度的模式
  ✅ 明确支持 Claude Code / Cursor / Cline 等编程工具
  ❌ 普通按量付费 API（没有专门的编程套餐包装）→ 不收录为 Part 2

【不收录】：
  ❌ 完全没有任何免费额度或编程套餐
  ❌ 仅面向内部使用，无公开 API
  ❌ 平台已关闭或服务已下线
```

---

## 三、提供商分批执行清单

> 将 131 家提供商分为 8 个批次。每个批次可独立并行执行。

### 批次 1：国内原始大模型厂商 A（10家）— 优先级最高

这些提供商在现有 README.md 中已有记录，需**验证并更新**至 2026 年 6 月最新状态。

```
执行清单：
  1.  百度智能云 (千帆)     — 官网: cloud.baidu.com        — 重点：代金券、ERNIE系列定价
  2.  阿里云 (百炼)          — 官网: bailian.console.aliyun.com — 重点：7000万Token验证、Coding Plan价格更新
  3.  字节跳动 (火山引擎)    — 官网: volcengine.com          — 重点：Coding Plan、教育专属1亿Token
  4.  腾讯云 (混元)          — 官网: cloud.tencent.com       — 重点：Hunyuan-lite免费状态
  5.  华为云 (盘古)          — 官网: huaweicloud.com         — 重点：1元购千万Token活动
  6.  智谱AI                 — 官网: bigmodel.cn             — 重点：2000万Token、GLM Coding Plan涨价后价格
  7.  深度求索 (DeepSeek)    — 官网: platform.deepseek.com   — 重点：500万Token、有效期
  8.  月之暗面 (Moonshot AI) — 官网: platform.moonshot.cn    — 重点：新检索免费额度
  9.  百川智能               — 官网: platform.baichuan-ai.com — 重点：新检索免费额度
  10. 零一万物 (01.AI)       — 官网: platform.lingyiwanwu.com — 重点：新检索免费额度
```

### 批次 2：国内原始大模型厂商 B（20家）— 优先级高

大部分为现有 README 未收录的提供商，需**全新检索**。

```
执行清单：
  1.  阶跃星辰 (StepFun)  — 官网: platform.stepfun.com     — 已有部分信息，需验证
  2.  MiniMax (稀宇科技)   — 官网: platform.minimaxi.com    — Coding Plan验证
  3.  商汤科技 (大装置)    — 官网: platform.sensenova.cn     — 0元购计划验证
  4.  科大讯飞             — 官网: xinghuo.xfyun.cn          — Lite永久免费验证
  5.  面壁智能             — 官网: modelbest.cn              — 新检索
  6.  昆仑万维             — 官网: model.tiangong.cn         — 新检索
  7.  360智脑              — 官网: ai.360.com                — 新检索
  8.  出门问问             — 官网: openapi.mobvoi.com        — 新检索
  9.  小米 (MiMo)          — 官网: platform.xiaomimimo.com   — 新检索：API价格下调
  10. 京东 (言犀)          — 官网: console.jdcloud.com       — 新检索
  11. 美团 (LongCat)       — 官网: longcat.chat/platform     — 新检索
  12. vivo (蓝心)          — 官网: dev.vivo.com.cn           — 新检索
  13. OPPO (安第斯)        — 官网: open.oppomobile.com       — 新检索
  14. 第四范式 (式说)      — 官网: 4paradigm.com             — 新检索
  15. 云知声 (山海)        — 官网: unisound.com              — 新检索
  16. 紫东太初             — 官网: taichu-web.ia.ac.cn       — 新检索
  17. 浪潮信息 (源)        — 官网: yuan.inspur.com           — 新检索
  18. 达观数据 (曹植)      — 官网: datagrand.com             — 新检索
  19. 云从科技 (从容)      — 官网: cloudwalk.com             — 新检索
  20. 快手 (可图/意间)     — 官网: klingai.kuaishou.com      — 新检索
```

### 批次 3：国内算力/聚合云服务平台（16家）— 优先级高

```
执行清单：
  1.  硅基流动 (SiliconFlow) — 官网: cloud.siliconflow.cn   — 验证2000万Token
  2.  无问芯穹 (Infini-AI)   — 官网: cloud.infini-ai.com    — 验证百亿Token、Coding Plan
  3.  白山云 AI               — 官网: ai.baishan.com          — 验证450元体验金
  4.  PPIO 派欧云             — 官网: ppio.com                — 验证5元额度
  5.  摩尔线程 AI             — 官网: code.mthreads.com       — 验证Coding Plan
  6.  AiHubMix                — 官网: aihubmix.com            — 验证免费模型列表
  7.  中国移动 MoMA           — 官网: cloud.10086.cn          — 新检索
  8.  中国电信 (天翼AI)       — 官网: teleai.com.cn           — 新检索
  9.  中国联通 (元景)         — 官网: maas.ai-yuanjing.com    — 新检索
  10. 非线智能 (NoneLinear)   — 官网: nonelinear.com          — 新检索
  11. DMXAPI                  — 官网: dmxapi.com              — 新检索
  12. 网易有道 ThinkFlow      — 官网: ai.youdao.com           — 新检索
  13. 猎户星空                — 官网: ainirobot.com           — 新检索
  14. 知乎 (知海图AI)         — 官网: zhihai.zhihu.com        — 新检索
  15. StreamLake (快手)       — 官网: streamlake.ai           — 新检索
  16. 数眼智能 (DataEye)      — 官网: dataeye.com             — 新检索
```

### 批次 4：国外原始大模型厂商 A（15家）— 优先级中

```
执行清单：
  1.  OpenAI              — 官网: platform.openai.com
  2.  Anthropic           — 官网: console.anthropic.com
  3.  Google (AI Studio)  — 官网: aistudio.google.com
  4.  Google Cloud (Vertex AI) — 官网: cloud.google.com/vertex-ai
  5.  Meta (Llama)        — 官网: llama.meta.com
  6.  Mistral AI          — 官网: console.mistral.ai
  7.  Cohere              — 官网: dashboard.cohere.com
  8.  xAI                 — 官网: console.x.ai
  9.  AI21 Labs           — 官网: studio.ai21.com
  10. Upstage             — 官网: console.upstage.ai
  11. Reka AI             — 官网: api.reka.ai
  12. Jina AI             — 官网: jina.ai
  13. Perplexity          — 官网: docs.perplexity.ai
  14. Stability AI        — 官网: platform.stability.ai
  15. Writer AI           — 官网: dev.writer.com
```

### 批次 5：国外原始大模型厂商 B（12家）— 优先级中

```
执行清单：
  1.  Aleph Alpha         — 官网: aleph-alpha.com
  2.  Inflection AI       — 官网: inflection.ai
  3.  Amazon (Nova)       — 官网: nova.amazon.com
  4.  Oracle (OCI AI)     — 官网: cloud.oracle.com/ai
  5.  IBM (watsonx)       — 官网: ibm.com/watsonx
  6.  Databricks (Mosaic AI) — 官网: databricks.com
  7.  Clarifai            — 官网: clarifai.com
  8.  Black Forest Labs   — 官网: bfl.ai
  9.  Liquid AI           — 官网: liquid.ai
  10. Poolside            — 官网: poolside.ai
  11. Salesforce (Einstein) — 官网: developer.salesforce.com
  12. Snowflake (Cortex AI) — 官网: snowflake.com
```

### 批次 6：国外云服务/聚合平台 A（15家）— 优先级高

```
执行清单：
  1.  OpenRouter           — 官网: openrouter.ai          — 验证25+免费模型
  2.  Microsoft Azure OpenAI — 官网: azure.microsoft.com  — 新检索
  3.  AWS Bedrock          — 官网: aws.amazon.com/bedrock  — 新检索
  4.  Groq                 — 官网: console.groq.com        — 验证永久免费层
  5.  Cerebras             — 官网: cloud.cerebras.ai       — 验证免费层+Code订阅
  6.  Together AI          — 官网: api.together.ai         — 新检索
  7.  Anyscale             — 官网: app.endpoints.anyscale.com — 新检索
  8.  DeepInfra            — 官网: deepinfra.com           — 新检索
  9.  Fireworks AI         — 官网: fireworks.ai            — 验证$1额度
  10. Replicate            — 官网: replicate.com           — 新检索
  11. Nebius               — 官网: studio.nebius.com       — 验证$100额度
  12. SambaNova Cloud      — 官网: cloud.sambanova.ai      — 验证$5额度
  13. Hyperbolic           — 官网: app.hyperbolic.xyz      — 验证推荐奖励
  14. Modal                — 官网: modal.com               — 验证$30/月
  15. Lepton AI            — 官网: lepton.ai               — 验证Basic免费
```

### 批次 7：国外云服务/聚合平台 B（20家）— 优先级低

```
执行清单：
  1.  Hugging Face Endpoints — 官网: huggingface.co
  2.  Novita AI              — 官网: novita.ai
  3.  Cloudflare Workers AI  — 官网: ai.cloudflare.com
  4.  Lambda (Lambda Labs)   — 官网: lambda.ai
  5.  OVHcloud AI Endpoints  — 官网: endpoints.ai.cloud.ovh.net
  6.  RunPod                 — 官网: runpod.io
  7.  CoreWeave              — 官网: coreweave.com
  8.  kluster.ai             — 官网: kluster.ai
  9.  BentoCloud             — 官网: bentoml.com
  10. OctoAI                 — 官网: octoai.cloud
  11. DigitalOcean (GenAI)   — 官网: digitalocean.com
  12. Inference.net          — 官网: inference.net
  13. ShareAI                — 官网: shareai.now
  14. NVIDIA NIM             — 官网: build.nvidia.com
  15. AkashML                — 官网: akash.network
  16. AtlasCloud             — 官网: atlascloud.ai
  17. Avian                  — 官网: avian.io
  18. BaseTen                — 官网: baseten.co
  19. Chutes                 — 官网: chutes.ai
  20. Cirrascale             — 官网: cirrascale.com
```

### 批次 8：国外云服务/聚合平台 C（24家）— 优先级低

```
执行清单：
  1.  Crusoe          — 官网: crusoe.ai
  2.  DekaLLM         — 官网: cloudeka.id
  3.  Featherless     — 官网: featherless.ai
  4.  FriendliAI      — 官网: friendli.ai
  5.  GMICloud        — 官网: gmicloud.ai
  6.  InceptionLabs   — 官网: inceptionlabs.ai
  7.  Inceptron       — 官网: inceptron.io
  8.  InferenceNet    — 官网: inference.net
  9.  Infermatic      — 官网: infermatic.ai
  10. Ionstream       — 官网: ionstream.ai
  11. Mancer          — 官网: mancer.tech
  12. Mara            — 官网: mara.com
  13. ModelRun        — 官网: modelrun.org
  14. Morph Labs      — 官网: morphllm.com
  15. NCompass        — 官网: ncompass.tech
  16. Parasail        — 官网: parasail.io
  17. Perceptron      — 官网: perceptron.inc
  18. Phala Network   — 官网: phala.network
  19. Relace          — 官网: relace.ai
  20. Modular         — 官网: modular.com
  21. Sourceful       — 官网: sourceful.com
  22. Venice          — 官网: venice.ai
  23. Weights & Biases — 官网: wandb.ai
  24. Z.AI            — 官网: chat.z.ai
```

---

## 四、输出格式规范

### 4.1 Part 1 单个提供商输出格式

```markdown
### {序号}. {提供商中文名}（{提供商英文名}）

| 字段 | 详情 |
|------|------|
| **平台名称** | [{提供商名称}]({官方URL}) |
| **注册福利** | {具体赠送内容，使用**加粗**标注核心数字} |
| **有效期** | **{永久/X天/限时}** |
| **邀请/拉新奖励** | {具体内容 或 "未查到"} |
| **学生福利** | {具体内容 或 "未查到"} |
| **前置条件** | {注册要求} |
| **备注** | {支持模型、特色、补充信息} |
```

**格式要点**：
- 核心数字（Token数、金额、天数）用 `**加粗**` 标注
- 多条信息用分号 `;` 分隔
- 活动时间用"2026.X.X~X.X"格式
- "未查到"表示经过搜索确实没找到，不是没搜索

### 4.2 Part 2 单个提供商输出格式

```markdown
### {序号}. {提供商名称} {套餐品牌名}

| 字段 | 详情 |
|------|------|
| **平台名称** | [{套餐全名}]({套餐URL}) |
| **套餐档位与价格** | **{档位名}**：{价格/月}（{优惠信息}）<br>{更多档位...} |
| **支持模型** | {可用模型列表} |
| **调用限制** | **{档位名}**：{具体限制}<br>{更多档位...} |
| **首月优惠** | ✅ {具体价格} 或 ❌ {原因} |
| **兼容工具** | {IDE/工具列表} |
| **备注** | {其他特色信息} |
```

### 4.3 编程订阅横向对比表格式

```markdown
## 编程订阅计划横向对比速览

| 对比项 | {平台1} | {平台2} | {平台3} | ... |
|--------|---------|---------|---------|-----|
| **入门月费** | {价格} | {价格} | {价格} | ... |
| **首月优惠** | ✅/❌ {价格} | ... | ... | ... |
| **最低体验价** | {价格} | ... | ... | ... |
| **Lite 5h额度** | {次数} | ... | ... | ... |
| **Pro 5h额度** | {次数} | ... | ... | ... |
| **重置机制** | {机制} | ... | ... | ... |
| **模型数量** | {数量} | ... | ... | ... |
| **多模型切换** | ✅/❌ | ... | ... | ... |
| **计量单位** | {单位} | ... | ... | ... |
| **性价比** | {一句话总结} | ... | ... | ... |
```

### 4.4 综合推荐格式

```markdown
## 📊 综合推荐

### 白嫖推荐 TOP 5

| 排名 | 平台 | 推荐理由 |
|------|------|---------| 
| 🥇 | **{平台名}** | {一句话理由} |
| 🥈 | **{平台名}** | {一句话理由} |
| 🥉 | **{平台名}** | {一句话理由} |
| 4 | **{平台名}** | {一句话理由} |
| 5 | **{平台名}** | {一句话理由} |

### 编程订阅推荐

| 需求场景 | 推荐平台 | 理由 |
|---------|---------|------|
| **最低月费入门** | {平台} | {理由} |
| **最低首月体验** | {平台} | {理由} |
| **免费试用** | {平台} | {理由} |
| **重度开发(国内)** | {平台} | {理由} |
| **最强模型(国内)** | {平台} | {理由} |
| **多模型灵活** | {平台} | {理由} |
| **极速推理(海外)** | {平台} | {理由} |
```

---

## 五、完整 README.md 结构模板

```markdown
# FreeLLM-API-KeyHub 🆓

本项目旨在整理可免费调用大模型API的服务商资源，持续更新中...
实时追踪大模型平台免费资源 | [English](README_EN.md) | [更新日志](#更新日志) | [提交情报](CONTRIBUTING.md)

实时追踪国内大模型厂商的**免费API资源**与**限时模型调用**情报
⚠️ 本仓库不提供任何API Key，仅汇总官方公开的免费资源信息 ⚠️

> **👉 建议查看在线文档：[点击访问在线文档（第一时间更新）](https://my.feishu.cn/wiki/PrlGwiZDAiKzUYklstqcQyXsnrh?from=from_copylink)**

> **👉 GitHub 开源地址：[FreeLLM-API-KeyHub](https://github.com/guihuashaoxiang/FreeLLM-API-KeyHub)**

**✨ 有其他可以白嫖的资源欢迎提交issues或PR！✨**

🤖 **全自动龙虾托管声明** 🦞🦞🦞

> 声明：[保留原有声明内容]

---

## Part 1：白嫖指南（免费额度检索）

> 以下平台面向**个人用户**，注册后可获得**实实在在的免费额度**。

---

[Part 1 各提供商详情，按照额度慷慨程度排序]

---

## Part 2：编程订阅计划对比（Coding Plan / 编程套餐）

> 以下平台提供面向 AI 编程场景的**包月/订阅计划**，固定月费提供大量 API 调用额度。
> 注意：不同平台的命名不同——有的叫 Coding Plan，有的叫编程套餐 / 编码套餐。

---

[Part 2 各提供商详情]

---

## 编程订阅计划横向对比速览

[对比表格]

---

## 📊 综合推荐

[白嫖推荐 + 编程订阅推荐]

---

> ⚠️ **免责声明**：以上信息基于{当前日期}逐一访问各平台官网整理，政策随时可能调整。部分免费额度需满足特定条件（实名认证、限时活动等），请以官方最新公告为准。

---

## 推荐工具 🧰

[保留原有工具推荐]

---

## 致谢 💖

[保留原有致谢内容]
```

---

## 六、质量要求与注意事项

### 6.1 信息准确性

```
✅ 必须做到：
  - 每条信息都有官方网页来源支撑
  - Token 数量、金额、有效期等核心数据必须精确
  - 活动截止日期必须注明，过期活动需标注"已过期"
  - 区分"个人用户"和"企业用户"的福利

❌ 严禁出现：
  - 凭搜索摘要猜测的信息
  - 过时信息当作最新信息
  - 混淆不同产品线的优惠（如把云服务优惠当作 API 优惠）
  - 遗漏重要限制条件
```

### 6.2 时效性处理

```
当前时间：2026年6月

判断规则：
  - 活动截止日期在 2026年6月之前 → 标注"已过期"或不收录
  - 活动截止日期在 2026年6月之后 → 正常收录，注明截止日期
  - "永久免费" → 需验证当前是否仍然有效
  - "限时免费" 但未注明截止日期 → 标注"限时（截止日期未知）"
```

### 6.3 排序规则

```
Part 1 排序依据（综合考量）：
  1. 免费额度的绝对价值（金额或Token数）
  2. 有效期长度（永久 > 1年 > 90天 > 30天）
  3. 使用便利性（无需实名 > 需实名 > 需企业认证）
  4. 模型质量与种类
  5. 额外福利（邀请奖励、学生优惠等）

Part 2 排序依据：
  1. 入门门槛（首月价格 / 最低月费）
  2. 性价比（调用额度 / 价格）
  3. 模型覆盖度
  4. 工具兼容性
```

### 6.4 常见陷阱提醒

```
⚠️ 检索时需特别注意：

1. 【代金券 vs Token】：代金券是钱（可抵扣API费用），Token是调用量，不要混淆
2. 【平台额度 vs 模型额度】：有的平台是"每个模型"送X Token，总量要乘以模型数
3. 【输入Token vs 输出Token】：价格通常不同，注意区分
4. 【免费层限速】：永久免费往往有严格的 RPM/RPD 限制，必须注明
5. 【新用户定义】：有的平台"新用户"指首次注册，有的指首次开通某服务
6. 【Coding Plan 的"次数"】：一次用户提问可能触发 5-30 次模型调用，注意换算
7. 【试用 vs 免费层】：试用过期后需付费 ≠ 永久免费层
8. 【地区限制】：部分国外平台可能限制中国大陆用户
```

---

## 七、中间产出物

执行过程中，建议产出以下中间文件以便追溯：

### 7.1 检索记录文件（每批次一个）

文件名：`research_batch_{N}_results.md`

```markdown
# 批次 {N} 检索记录

## {提供商名称}

### 搜索记录
- 关键词1: "{搜索词}" → 结果摘要
- 关键词2: "{搜索词}" → 结果摘要

### 访问页面
- {URL1} → 页面核心信息摘要
- {URL2} → 页面核心信息摘要

### 提取结果
- Part 1: ✅/❌（收录/不收录）
- Part 2: ✅/❌（收录/不收录）
- 具体信息: [填写提取的字段]

---
[下一个提供商]
```

### 7.2 汇总裁定文件

文件名：`research_summary.md`

```markdown
# 全量检索汇总

| 序号 | 提供商 | Part 1 | Part 2 | 免费额度概要 | 编程套餐概要 |
|------|--------|--------|--------|-------------|-------------|
| 1 | 百度千帆 | ✅ | ❌ | 20元代金券 | 无 |
| 2 | 阿里百炼 | ✅ | ✅ | 7000万Token | Lite 40元/月 |
| ... | ... | ... | ... | ... | ... |
```

---

## 八、执行控制

### 8.1 并行执行建议

```
可并行的批次组合（无依赖关系）：
  - 组 A：批次1 + 批次4（国内厂商A + 国外厂商A）
  - 组 B：批次2 + 批次5（国内厂商B + 国外厂商B）
  - 组 C：批次3 + 批次6（国内聚合 + 国外聚合A）
  - 组 D：批次7 + 批次8（国外聚合B + 国外聚合C）

推荐执行顺序：组A → 组B → 组C → 组D
理由：优先处理已有数据需要验证的高优提供商
```

### 8.2 进度检查点

```
检查点 1：批次1+4 完成 → 产出 25 家提供商检索结果
检查点 2：批次2+5 完成 → 累计 57 家
检查点 3：批次3+6 完成 → 累计 88 家（含所有高优提供商）
检查点 4：批次7+8 完成 → 全部 131 家

每个检查点：
  - 核对已检索数量
  - 检查是否有遗漏
  - 汇总 Part 1 / Part 2 候选列表
  - 评估是否需要调整后续批次的搜索策略
```

### 8.3 异常处理

```
如果遇到以下情况：

1. 官网无法访问（超时/404）：
   → 记录为"官网暂不可达"，尝试搜索缓存页面或第三方报道
   → 标注为"待复核"

2. 搜索无任何相关结果：
   → 尝试更换关键词（用产品名替代公司名，或反之）
   → 尝试搜索"{name} API documentation"
   → 如仍无结果，记录为"未找到公开API服务信息"

3. 信息矛盾（不同来源数据不一致）：
   → 以官方网站信息为准
   → 如官方信息也不一致（如旧页面vs新页面），取最新日期的信息

4. 仅有企业版/内测邀请：
   → 记录现状，不收录进 Part 1
   → 标注"需企业认证"或"需内测邀请"
```

---

## 九、最终交付物清单

```
必须交付：
  ├── README.md                    ← 最终展示文档（Part 1 + Part 2 + 对比表 + 推荐）
  ├── research_summary.md          ← 131家提供商检索汇总裁定表
  └── research_batch_{1-8}_results.md ← 各批次详细检索记录（8个文件）

README.md 预期内容规模：
  - Part 1：预计 25-35 家提供商（从131家中筛选）
  - Part 2：预计 7-12 家提供商（从131家中筛选）
  - 横向对比表：覆盖所有 Part 2 提供商
  - 综合推荐：TOP 5 白嫖 + 7-10 个场景推荐
```

---

> 📌 **执行此任务前，请先完整阅读本提示词，理解每个步骤的要求。执行过程中严格按照检索方法论操作，不要跳过任何步骤。**
