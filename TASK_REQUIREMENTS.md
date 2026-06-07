# 任务需求文档：重建国内外大模型 API 调用服务提供商全量列表

> 📅 创建时间：2026-06-06  
> 📅 最后更新：2026-06-06  
> 📂 所属项目：FreeLLM-API-KeyHub  
> 🎯 任务状态：  
> - ✅ 第一阶段（全量列表基础重建）── 已完成，89 家  
> - 🔄 第二阶段（深度检索扩展）── 进行中

---

## 一、任务背景

本项目 **FreeLLM-API-KeyHub** 是一个开源仓库，其核心目标是整理可免费调用大模型 API 的服务商资源。项目原本维护有一份**国内外大模型 API 调用服务提供商的 Markdown 表格列表文件**，该文件记录了市场上所有已知的大模型 API 服务提供商（不限于免费资源），作为全量数据源存在。

项目当前的 `README.md` 文件是从该全量列表中**筛选出具有免费或白嫖属性的服务商**后，精心整理而成的最终开源展示文档。

**问题**：该全量列表源文件已丢失，需要重建。

---

## 二、任务目标

重建一份**详尽、完整、准确**的国内外大模型 API 调用服务提供商全量汇总 Markdown 表格文件。

**目标规模**：120+ 家提供商（第一阶段已完成 89 家，第二阶段目标通过深度检索补充至 120+ 家）。

---

## 三、详细需求

### 3.1 检索范围

1. **不区分是否免费**：全量收录国内外所有主流大模型 API 调用服务提供商，无论其是否提供免费额度、白嫖机会或仅为纯付费服务。
2. **必须足够详尽**：覆盖范围应包括但不限于：
   - **国内原始大模型厂商**（如百度、阿里、字节、腾讯、华为、智谱、DeepSeek、月之暗面、百川、零一万物、阶跃星辰、MiniMax、商汤、科大讯飞、面壁智能、昆仑万维、360、出门问问、小米、京东、美团、vivo、OPPO、第四范式、云知声、紫东太初等）
   - **国内算力/聚合云服务平台**（如硅基流动、无问芯穹、白山云、PPIO、摩尔线程、AiHubMix、中国移动MoMA、中国电信天翼AI、中国联通元景、非线智能、DMXAPI 等）
   - **国外原始大模型厂商**（如 OpenAI、Anthropic、Google、Meta、Mistral AI、Cohere、xAI、AI21 Labs、Upstage、Reka AI、Jina AI、Perplexity、Stability AI、Writer AI、Aleph Alpha、Inflection AI、Amazon Nova、IBM watsonx、Oracle OCI AI、Databricks、Clarifai 等）
   - **国外云服务/算力/聚合平台**（如 OpenRouter、Azure OpenAI、AWS Bedrock、Groq、Cerebras、Together AI、Anyscale、DeepInfra、Fireworks AI、Replicate、Nebius、SambaNova、Hyperbolic、Modal、Lepton AI、Hugging Face、Novita AI、Cloudflare Workers AI、Lambda Labs、OVHcloud、RunPod、CoreWeave、kluster.ai、BentoCloud、OctoAI、DigitalOcean 等）
3. **深度检索与关联检索**：以 `README.md` 中已收录的服务商为起点，通过关联检索扩展发现更多未被收录的提供商。

### 3.2 输出文件要求

1. **独立文件**：检索结果单独存放为一个 Markdown 文件，不写入 `README.md`。
2. **文件位置**：存放于当前项目根目录下。
3. **文件名称**：`LLM_API_Providers_All.md`
4. **表格字段**：每个服务提供商记录必须包含以下三列：
   - **服务提供商名**：平台/公司名称（中英文）
   - **访问地址**：官方平台或 API 控制台的 URL 链接
   - **必要说明**：简要描述该平台的核心模型、定位或特色优势
5. **分类组织**：按以下维度进行分类：
   - 国内 vs 国外
   - 原始大模型厂商 vs 算力/聚合云服务平台

### 3.3 文件用途定位

- 本文件定位为**全量数据源/检索底稿**。
- 后续将基于此文件进行筛选，从中提取出具有免费或白嫖属性的服务商信息，更新至 `README.md` 中。
- 本文件本身**不涉及**免费额度、白嫖攻略等筛选后的详细信息。

---

## 四、与现有文件的关系

```
LLM_API_Providers_All.md（全量列表 - 本次重建目标）
        │
        │  筛选出免费/白嫖属性的提供商
        ▼
README.md（筛选后的最终开源展示文档 - 已存在）
  ├── Part 1：白嫖指南（免费额度检索）── 24 家提供商详情
  ├── Part 2：编程订阅计划对比 ── 7 家提供商详情
  └── 综合推荐排行
```

---

## 五、验收标准

### 5.1 第一阶段验收（已通过 ✅）

1. ✅ 文件 `LLM_API_Providers_All.md` 已创建于项目根目录下
2. ✅ 表格涵盖国内外所有主流大模型 API 调用服务提供商（89 家，超过 50+ 要求）
3. ✅ 每个提供商包含名称、访问地址、必要说明三个字段
4. ✅ 按国内/国外、原始厂商/聚合平台进行了清晰分类
5. ✅ `README.md` 中已有的所有提供商均已包含在全量列表中
6. ✅ Markdown 表格格式正确，可正常渲染

### 5.2 第二阶段验收标准

1. ⬜ 通过深度检索方法论（见第七章）系统性扩展提供商列表至 **120+ 家**
2. ⬜ 新增提供商均经过**来源验证**（至少有一个可信数据源交叉验证）
3. ⬜ 每个新增提供商的**访问地址 URL 已验证可达**
4. ⬜ 无重复条目
5. ⬜ 覆盖第七章所述的全部 8 个数据源渠道的检索结果

---

## 六、第一阶段完成总结

| 维度 | 数量 |
|------|------|
| 国内原始大模型厂商 | 25 家 |
| 国内算力/聚合云服务平台 | 14 家 |
| 国外原始大模型厂商 | 22 家 |
| 国外云服务/算力/聚合平台 | 28 家 |
| **合计** | **89 家** |

---

## 七、第二阶段：深度检索方法论（核心扩展策略）

> 第一阶段通过基础网络搜索已收录 89 家提供商。要突破至 120+ 家，需要系统性地利用以下 **8 大数据源渠道** 进行深度检索。

### 7.1 GitHub 开源 Awesome Lists 交叉比对

**原理**：GitHub 上有多个社区维护的 LLM API 提供商精选列表，这些列表由全球开发者贡献和审核，覆盖了许多小众但真实可用的平台。

**具体数据源**：
- [`mnfst/awesome-free-llm-apis`](https://github.com/mnfst/awesome-free-llm-apis) — 专注永久免费层 LLM API，含速率限制和兼容性详情
- [`cheahjs/free-llm-api-resources`](https://github.com/cheahjs/free-llm-api-resources) — 分类为"免费提供商"和"试用额度提供商"
- [`ShaikhWarsi/free-ai-tools`](https://github.com/ShaikhWarsi/free-ai-tools) — 生产级 AI 工具和 API 综合列表
- 其他 `awesome-llm`、`awesome-ai-apis` 等相关仓库

**操作方法**：逐一读取上述仓库 README 内容，与现有 `LLM_API_Providers_All.md` 进行 Diff 比对，提取出未被收录的提供商。

### 7.2 LLM 代理网关/SDK 支持列表反向提取

**原理**：LiteLLM、One-API、New-API 等开源 LLM 代理/网关项目需要为每个支持的提供商编写适配代码。其源码中的渠道列表 = 市面上真实存在且有 API 的提供商清单。

**具体数据源**：
- **LiteLLM**（`BerriAI/litellm`）：支持 **140+ 提供商**，2700+ 模型。查看其 `litellm/llms/` 目录或文档 Providers 页面
- **One-API**（`songquanpeng/one-api`）：国内最流行的 API 管理系统，后台预设渠道列表涵盖所有主流国内外厂商
- **New-API**（`Calciumion/new-api`）：One-API 增强版，额外支持 Midjourney、Suno 等特殊服务
- **Vercel AI SDK**（`ai`包）：查看其 `providers/` 目录，每个适配器对应一个提供商

**操作方法**：
```bash
# 示例：从 LiteLLM 源码提取所有支持的提供商
git clone https://github.com/BerriAI/litellm
ls litellm/litellm/llms/  # 每个子目录 = 一个提供商
```

### 7.3 OpenRouter 提供商 API 实时抓取

**原理**：OpenRouter 作为全球最大的模型聚合网关，其后端对接了 **60+ 推理提供商**。通过其公开 API 可获取实时的完整提供商清单。

**操作方法**：
```bash
# 获取所有提供商列表
curl https://openrouter.ai/api/v1/providers

# 获取所有模型列表（含提供商信息）
curl https://openrouter.ai/api/v1/models
```

**价值**：可以发现许多专注推理优化的小型提供商（如某些区域性的 GPU 算力平台），这些在常规搜索中不易发现。

### 7.4 中国网信办大模型备案名录

**原理**：根据《生成式人工智能服务管理暂行办法》，国内所有提供大模型 API 的企业均须在网信办完成备案。截至 2026 年 4 月，全国已有 **868 款**生成式 AI 服务完成备案。备案名录 = 国内合法运营的大模型全集。

**具体数据源**：
- **官方查询**：[国家互联网信息办公室算法备案系统](https://beian.cac.gov.cn) — 最权威来源
- **第三方导航**：[隐拓智安备案导航](https://intokentech.cn) — 支持按产品名、主体、省份检索
- **信通院报告**：中国信息通信研究院定期发布的大模型产业报告

**操作方法**：从备案列表中提取提供 API 服务的企业，逐一核实其是否有公开 API 平台，补充至全量列表。

### 7.5 VC 投融资与行业研究报告

**原理**：获得融资的 AI 初创企业通常都会开放 API 以获取收入。追踪投融资事件可以发现新兴但尚未广为人知的提供商。

**具体数据源**：
- **Crunchbase / PitchBook**：搜索 `LLM API`、`AI inference`、`model serving` 相关融资事件
- **36氪 / 量子位 / 机器之心**：国内 AI 产业媒体的融资报道和行业盘点文章
- **CB Insights / a16z AI Reports**：每季度发布 AI 市场地图和竞争格局分析
- **Y Combinator**：YC 每期 batch 中的 AI/ML 初创企业

**关键搜索词**：
- 中文：`大模型API融资`、`AI推理云融资`、`大模型创业公司盘点`
- 英文：`LLM inference startup funding`、`AI API series A`、`model serving raised`

### 7.6 开发者社区与技术论坛深挖

**原理**：开发者在论坛中分享真实使用经验时，常常提到小众但好用的平台，这些平台在搜索引擎排名可能不高。

**具体数据源**：
- **Reddit**：`r/LocalLLaMA`、`r/MachineLearning`、`r/ChatGPT` — 搜索 "API provider"、"inference"
- **V2EX / 知乎**：搜索 `大模型API`、`AI接口`、`推理平台` 相关讨论
- **Discord**：各 AI 项目的 Discord 社区（如 Cline、Cursor 社区常讨论平价 API 替代方案）
- **Hacker News**：搜索 "Show HN" + "LLM API" 或 "inference"
- **Product Hunt**：AI / Developer Tools 分类下新发布的 API 平台

### 7.7 技术媒体对比测评文章

**原理**：深度对比测评文章为了全面性，会将市面上尽可能多的提供商纳入比较表格。这些表格是极好的交叉参考源。

**具体数据源**：
- **英文**：搜索 `"best LLM API providers" comparison 2026`、`"LLM inference" benchmark pricing`
- **中文**：搜索 `大模型API对比测评 2026`、`AI推理平台横向评测`
- **知名博客/媒体**：The Verge、TechCrunch、InfoQ、SegmentFault、CSDN 等的深度对比文章
- **YouTube / B站**：技术博主的 API 平台使用体验和横向对比视频

### 7.8 竞争对手文档交叉引用

**原理**：提供商之间存在竞争，各平台的官方对比文档和迁移指南中会提到竞品名称。

**操作方法**：
- 访问 OpenRouter、Together AI、DeepInfra 等聚合平台的文档，查看其 "Providers" 或 "Supported Models" 页面
- 查看硅基流动、无问芯穹等国内平台文档中提及的上游模型来源
- 搜索各平台的 `alternatives`（替代方案）页面，如 `OpenRouter alternatives`、`Groq competitors`

---

## 八、后续计划

### 第二阶段完成后
1. **去重与合并**：将所有渠道发现的新提供商与现有列表去重合并
2. **URL 验证**：使用脚本批量验证所有访问地址的可达性
3. **信息完善**：确保每个条目的"必要说明"字段准确且有信息量

### 长期维护
1. **定期检索更新**：每月通过上述方法论中的自动化渠道（如 OpenRouter API、LiteLLM 更新日志）追踪新提供商
2. **筛选免费资源**：从全量列表中筛选出提供免费额度或白嫖机会的服务商
3. **更新 README.md**：将筛选结果整理为详细的白嫖指南和编程订阅计划对比，更新至 README.md
4. **社区贡献**：鼓励开源社区通过 Issues/PR 提交新的提供商信息
