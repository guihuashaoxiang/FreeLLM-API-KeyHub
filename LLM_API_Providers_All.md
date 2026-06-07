# 国内外大模型 API 调用服务提供商全量汇总

> 📅 最后更新：2026-06-06
> 📂 所属项目：FreeLLM-API-KeyHub
> 📝 定位：全量数据源 / 检索底稿（不区分是否免费）

本文档旨在收集国内外所有主流大模型 API 调用服务提供商（不区分是否带有免费额度），作为全量检索资料，供后续筛选和二次整理使用。

---

## 一、国内大模型 API 提供商

### 1. 原始大模型厂商

| 服务提供商名 | 访问地址 | 必要说明 |
| --- | --- | --- |
| **百度智能云 (千帆)** | [https://cloud.baidu.com/product/wenxinworkshop](https://cloud.baidu.com/product/wenxinworkshop) | 提供文心一言 (ERNIE) 系列大模型（ERNIE 5.1/X1），国内生态较成熟，提供大量企业级微调工具。 |
| **阿里云 (百炼)** | [https://bailian.console.aliyun.com/](https://bailian.console.aliyun.com/) | 提供通义千问 (Qwen) 系列模型（Qwen3.5 等），同时也是聚合平台提供众多三方模型（如 DeepSeek、MiniMax、GLM）。 |
| **字节跳动 (火山引擎/火山方舟)** | [https://www.volcengine.com/product/doubao](https://www.volcengine.com/product/doubao) | 提供豆包 (Doubao) / Seed 系列模型，主打超高性价比和超强推理速度，生态接入广泛，支持 Coding Plan。 |
| **腾讯云 (混元)** | [https://cloud.tencent.com/product/hunyuan](https://cloud.tencent.com/product/hunyuan) | 提供腾讯混元系列模型，支持千亿级参数和万亿级MoE架构模型，以及出色的视频生成模型，Hunyuan-lite 完全免费。 |
| **华为云 (盘古)** | [https://www.huaweicloud.com/product/pangu.html](https://www.huaweicloud.com/product/pangu.html) | 提供盘古系列大模型，偏向政企和垂直行业落地场景，通过 ModelArts Studio 提供 MaaS 服务。 |
| **智谱AI** | [https://bigmodel.cn/](https://bigmodel.cn/) | 提供 GLM 系列 (GLM-4/GLM-5 等) 模型，中文语义、长文本理解和智能体构建能力极佳，支持 Coding Plan。 |
| **深度求索 (DeepSeek)** | [https://platform.deepseek.com/](https://platform.deepseek.com/) | 提供 DeepSeek-V3/V4/R1 等开源界顶流模型，以价格极低性能极强震撼行业，开发者生态极其活跃。 |
| **月之暗面 (Moonshot AI)** | [https://platform.moonshot.cn/](https://platform.moonshot.cn/) | 提供 Kimi 系列模型（K2.5/K2.6），以无损超长上下文处理能力闻名，在智能体场景中表现活跃。 |
| **百川智能** | [https://platform.baichuan-ai.com/](https://platform.baichuan-ai.com/) | 提供 Baichuan 系列模型，在医疗等垂类领域有深入优化。 |
| **零一万物 (01.AI)** | [https://platform.lingyiwanwu.com/](https://platform.lingyiwanwu.com/) | 提供 Yi 系列模型，在全球开源榜单中长期名列前茅。 |
| **阶跃星辰 (StepFun)** | [https://platform.stepfun.com/](https://platform.stepfun.com/) | 提供 Step 系列模型（如 Step-2/3.5 万亿参数语言大模型和优秀的多模态模型），支持"繁星计划"扶持。 |
| **MiniMax (稀宇科技)** | [https://platform.minimaxi.com/](https://platform.minimaxi.com/) | 提供 M2.5/M3 系列模型，语音生成、音乐创作和角色扮演能力极强，4M 超长上下文，支持 Coding Plan。 |
| **商汤科技 (大装置)** | [https://platform.sensenova.cn/](https://platform.sensenova.cn/) | 提供日日新 (SenseNova) 系列基础大模型及多模态能力，"大模型0元购计划"面向企业用户。 |
| **科大讯飞** | [https://xinghuo.xfyun.cn/](https://xinghuo.xfyun.cn/) | 提供星火认知大模型（星火 X2），在语音识别、合成和教育场景优势明显，Lite API 永久免费。 |
| **面壁智能** | [https://modelbest.cn/](https://modelbest.cn/) | 提供 MiniCPM 系列端侧及小参数量高效模型，性能极其越级，与知乎合作研发知海图AI。 |
| **昆仑万维** | [https://model.tiangong.cn/](https://model.tiangong.cn/) | 提供天工系列大模型及天工 SkyMusic 等音乐生成能力。 |
| **360智脑** | [https://ai.360.com/](https://ai.360.com/) | 提供 360 智脑系列模型，整合搜索引擎能力。 |
| **出门问问** | [https://openapi.mobvoi.com/](https://openapi.mobvoi.com/) | 提供序列猴子系列大模型，语音交互领域有深厚积累。 |
| **小米 (MiMo)** | [https://platform.xiaomimimo.com/](https://platform.xiaomimimo.com/) | 提供 MiMo-V2.5 系列模型，支持原生全模态（图文音视），兼容 OpenAI/Anthropic 协议，API 价格大幅下调。 |
| **京东 (言犀)** | [https://console.jdcloud.com/](https://console.jdcloud.com/) | 提供言犀系列模型（81B-Pro/750B），基于京东供应链产业数据，擅长智能体编排和工具调用。 |
| **美团 (LongCat)** | [https://longcat.chat/platform/](https://longcat.chat/platform/) | 提供 LongCat 系列大模型，具备轻量化对话、深度推理及视频数字人能力，兼容 OpenAI/Anthropic 协议。 |
| **vivo (蓝心)** | [https://dev.vivo.com.cn/](https://dev.vivo.com.cn/) | 提供蓝心 (BlueLM) 系列自研大模型，支持 32K 长文本，面向移动端侧及应用场景优化。 |
| **OPPO (安第斯)** | [https://open.oppomobile.com/](https://open.oppomobile.com/) | 提供安第斯 (AndesGPT) 大模型，"1+N"架构，主要服务 ColorOS 系统 AI 智能体和端侧计算。 |
| **第四范式 (式说)** | [https://www.4paradigm.com/](https://www.4paradigm.com/) | 主打 AIGS (AI-Generated Software) 战略，侧重企业级生成式 AI，擅长多模态和企业软件 Copilot。 |
| **云知声 (山海)** | [https://www.unisound.com/](https://www.unisound.com/) | 提供山海大模型 Token Hub 矩阵，侧重医保、智能交互等垂直行业应用。 |
| **紫东太初** | [https://taichu-web.ia.ac.cn/](https://taichu-web.ia.ac.cn/) | 由中科院自动化所研发，支持图文音三模态，紫东太初 4.0 强化多模态+深度推理能力。 |
| **浪潮信息 (源)** | [https://yuan.inspur.com/](https://yuan.inspur.com/) | 提供源 (Yuan) 系列基础大模型，全开源全免费，强调高质量中文语料和算力协同。 |
| **达观数据 (曹植)** | [https://www.datagrand.com/](https://www.datagrand.com/) | 提供曹植大模型，垂直于金融、政务等长文本处理、公文写作和业务自动化场景。 |
| **云从科技 (从容)** | [https://www.cloudwalk.com/](https://www.cloudwalk.com/) | 提供从容 (Congrong) 大模型，专注视觉、语音与跨模态交互，在安防、金融领域落地深厚。 |
| **快手 (可图/意间)** | [https://klingai.kuaishou.com/](https://klingai.kuaishou.com/) | 提供可图 (Kolors) 图像生成模型及 Kling 视频生成大模型，API 开放为开发者提供强大的视觉生成能力。 |

### 2. 算力/聚合云服务平台

| 服务提供商名 | 访问地址 | 必要说明 |
| --- | --- | --- |
| **硅基流动 (SiliconFlow)** | [https://cloud.siliconflow.cn/](https://cloud.siliconflow.cn/) | 国内领先的算力平台，聚合海量开源模型，主打超高性价比和极速推理引擎，注册送 2000 万 Tokens。 |
| **无问芯穹 (Infini-AI)** | [https://cloud.infini-ai.com/](https://cloud.infini-ai.com/) | 多模型聚合云平台，百亿 Tokens 免费配额，GenStudio LLM API 免费调用，支持 Coding Plan。 |
| **白山云 AI** | [https://ai.baishan.com/](https://ai.baishan.com/) | 基于全球边缘节点的云服务，聚合调用国产主流大模型，主打超低延迟，最高 ¥450 体验金。 |
| **PPIO 派欧云** | [https://ppio.com/](https://ppio.com/) | 提供去中心化算力基础设施，支持 DeepSeek 等主流开源模型推理，初创企业扶持最高 10 万元。 |
| **摩尔线程 AI** | [https://code.mthreads.com/](https://code.mthreads.com/) | 基于国产 GPU 硬件 (MTT S5000) 的算力平台，提供极具性价比的 Coding Plan，30 天免费试用。 |
| **AiHubMix** | [https://aihubmix.com/](https://aihubmix.com/) | 典型的国内外模型聚合中转服务，支持数百种模型一站式调用，多款模型永久免费。 |
| **中国移动 MoMA** | [https://cloud.10086.cn/](https://cloud.10086.cn/) | 中国移动推出的一站式模型服务平台，聚合九天大模型及 DeepSeek、Qwen、Kimi、GLM 等主流模型，具备央企合规优势。 |
| **中国电信 (天翼AI)** | [https://www.teleai.com.cn/](https://www.teleai.com.cn/) | 基于自研 TeleChat 大模型的天翼 AI 开放平台，提供多类 API 服务，侧重政企行业定制与企业级安全防护。 |
| **中国联通 (元景)** | [https://maas.ai-yuanjing.com/](https://maas.ai-yuanjing.com/) | 联通元景大模型 MaaS 平台，支持模型纳管、智能体编排，兼容 OpenAI 标准接口和 MCP 协议。 |
| **非线智能 (NoneLinear)** | [https://nonelinear.com/](https://nonelinear.com/) | 企业级 API 聚合平台，支持上百款模型及 OpenAI/Anthropic/Gemini 多协议转换，主打高可用与全链路透明。 |
| **DMXAPI** | [https://www.dmxapi.com/](https://www.dmxapi.com/) | 由 LangChain 中文网提供的 API 聚合服务，汇聚国内外超 100 个主流大模型，降低新手开发门槛。 |
| **网易有道 ThinkFlow** | [https://ai.youdao.com/](https://ai.youdao.com/) | 网易有道推出的大模型聚合平台，支持多模型无缝切换、智能路由及负载均衡，提供高可用 API 调用。 |
| **猎户星空** | [https://www.ainirobot.com/](https://www.ainirobot.com/) | 专注机器人场景，通过 AgentOS 结合大模型实现多模态交互与机器人自主决策。 |
| **知乎 (知海图AI)** | [https://zhihai.zhihu.com/](https://zhihai.zhihu.com/) | 与面壁智能合作自研，落地于知乎搜索和问答场景，致力于提供可信赖的优质信息。 |
| **StreamLake (快手)** | [https://www.streamlake.ai/](https://www.streamlake.ai/) | 快手旗下的 ToB 品牌，提供基于大模型的视频及图像处理 API 和企业级 AI 解决方案。 |
| **数眼智能 (DataEye)** | [https://www.dataeye.com/](https://www.dataeye.com/) | 提供大模型 API 聚合与调用服务，侧重于游戏、营销垂直场景的 AI 辅助创作。 |

---

## 二、国外大模型 API 提供商

### 1. 原始大模型厂商

| 服务提供商名 | 访问地址 | 必要说明 |
| --- | --- | --- |
| **OpenAI** | [https://platform.openai.com/](https://platform.openai.com/) | 提供 GPT-4o/GPT-5/o1/o3 等行业基准模型，全球开发者生态最丰富，工具调用和结构化输出最成熟。 |
| **Anthropic** | [https://console.anthropic.com/](https://console.anthropic.com/) | 提供 Claude 3/3.5/4 系列模型，代码生成和长文本逻辑推理能力卓越，Computer Use 功能领先。 |
| **Google (AI Studio)** | [https://aistudio.google.com/](https://aistudio.google.com/) | 供开发者使用的 Gemini API 平台，支持超长上下文（1M+ tokens），常有免费测试额度。 |
| **Google Cloud (Vertex AI)** | [https://cloud.google.com/vertex-ai](https://cloud.google.com/vertex-ai) | Google 面向企业的全托管 AI 平台，包含 Gemini 系列及众多三方模型，企业级 SLA 保障。 |
| **Meta (Llama)** | [https://llama.meta.com/](https://llama.meta.com/) | 提供 Llama 4/5 系列开源权重模型的官方 API，支持多模态，也可通过 Groq、Together AI 等三方调用。 |
| **Mistral AI** | [https://console.mistral.ai/](https://console.mistral.ai/) | 欧洲 AI 巨头，提供 Mistral Large 及 Codestral 等高质量高性价比模型，注重数据主权（EU 驻留）。 |
| **Cohere** | [https://dashboard.cohere.com/](https://dashboard.cohere.com/) | 专注于企业级 RAG、文本检索 (Rerank) 和多语种理解，Command R+ 系列表现出色。 |
| **xAI** | [https://console.x.ai/](https://console.x.ai/) | Elon Musk 旗下，提供 Grok 系列大模型 API，具备出色的数学/编码能力和超大上下文窗口。 |
| **AI21 Labs** | [https://studio.ai21.com/](https://studio.ai21.com/) | 提供 Jurassic 和结合 SSM 架构的 Jamba 系列大模型，在长文档处理和企业场景有独特优势。 |
| **Upstage** | [https://console.upstage.ai/](https://console.upstage.ai/) | 韩国领先 AI 企业，提供 Solar 系列模型及优秀文档解析 (Document AI) 能力。 |
| **Reka AI** | [https://api.reka.ai/](https://api.reka.ai/) | 提供 Reka Core/Flash/Edge 多模态大模型，核心团队来自 DeepMind/Google。 |
| **Jina AI** | [https://jina.ai/](https://jina.ai/) | 专注 Embedding、Reranker 检索相关 API 及 Reader/Search 联网接口，搜索增强领域标杆。 |
| **Perplexity** | [https://docs.perplexity.ai/](https://docs.perplexity.ai/) | 提供 Sonar 系列自带原生联网检索能力的 API，适合需要实时信息的场景。 |
| **Stability AI** | [https://platform.stability.ai/](https://platform.stability.ai/) | 提供 Stable Diffusion 3.5、Stable Image Ultra、Stable Audio 3.0 等图像/音频生成模型 API。 |
| **Writer AI** | [https://dev.writer.com/](https://dev.writer.com/) | 企业级全栈 AI 平台，提供自研 Palmyra X5 系列模型 API，支持 AI Agent 构建和 Knowledge Graph。 |
| **Aleph Alpha** | [https://aleph-alpha.com/](https://aleph-alpha.com/) | 欧洲主权 AI 企业，提供 Luminous/PhariaAI 系列模型，强调数据隐私、GDPR 合规和企业级安全。 |
| **Inflection AI** | [https://inflection.ai/](https://inflection.ai/) | 提供 Inflection 3 Pi 等模型，定位于高情商对话和会话式 AI，支持企业级 API 接入。 |
| **Amazon (Nova)** | [https://nova.amazon.com/](https://nova.amazon.com/) | 亚马逊自研 Nova 系列模型（Premier/Pro/Lite/Micro/Canvas/Reel/Sonic），支持文本/图像/视频/语音多模态。 |
| **Oracle (OCI AI)** | [https://cloud.oracle.com/ai](https://cloud.oracle.com/ai) | Oracle 企业级 AI 服务，嵌入 Fusion Cloud 应用，聚合 Grok、NVIDIA Nemotron 等模型，主权云优势。 |
| **IBM (watsonx)** | [https://www.ibm.com/watsonx](https://www.ibm.com/watsonx) | 企业级混合/本地 AI 平台，Granite 系列模型，强调严格数据治理、合规性和受监管行业适用性。 |
| **Databricks (Mosaic AI)** | [https://www.databricks.com/product/machine-learning](https://www.databricks.com/product/machine-learning) | 数据湖仓一体 AI 平台，擅长企业私有数据上的 RAG 和模型微调，与数据治理深度融合。 |
| **Clarifai** | [https://clarifai.com/](https://clarifai.com/) | 专注计算机视觉和多模态 AI，提供图像/视频/音频非结构化数据处理 API，视觉 AI 领域老牌玩家。 |
| **Black Forest Labs** | [https://bfl.ai/](https://bfl.ai/) | FLUX 系列图像生成大模型的创造者，提供官方的高质量生图 API (BFL API)。 |
| **Liquid AI** | [https://www.liquid.ai/](https://www.liquid.ai/) | 开创液态基础模型 (LFMs) 架构，提供高效率、极低内存占用的序列模型 API。 |
| **Poolside** | [https://poolside.ai/](https://poolside.ai/) | 专注于软件开发领域的 AI 模型，提供强大的代码补全、生成与理解 API 接口。 |
| **Salesforce (Einstein)** | [https://developer.salesforce.com/](https://developer.salesforce.com/) | 提供 Einstein Trust Layer 及企业级 AI API，深度集成 CRM 系统。 |
| **Snowflake (Cortex AI)** | [https://www.snowflake.com/](https://www.snowflake.com/) | 专为数据云原生设计的 AI 平台，提供安全托管的主流大模型推理 API。 |

### 2. 云服务/算力/聚合平台

| 服务提供商名 | 访问地址 | 必要说明 |
| --- | --- | --- |
| **OpenRouter** | [https://openrouter.ai/](https://openrouter.ai/) | 全球最著名的模型聚合网关，统一接口支持数百种模型，提供透明比价，25+ 免费模型永久可用。 |
| **Microsoft Azure OpenAI** | [https://azure.microsoft.com/](https://azure.microsoft.com/) | 微软企业云，提供极其合规、企业级 SLA 的 OpenAI 模型接口调用，HIPAA/SOC2 合规。 |
| **AWS Bedrock** | [https://aws.amazon.com/bedrock/](https://aws.amazon.com/bedrock/) | 亚马逊的全托管服务，聚合 Claude、Llama、Mistral、Nova、Titan 等多家大模型。 |
| **Groq** | [https://console.groq.com/](https://console.groq.com/) | 基于自研 LPU 硬件，提供极其夸张的 Llama、DeepSeek 闪电级推理速度，永久免费层全模型可用。 |
| **Cerebras** | [https://cloud.cerebras.ai/](https://cloud.cerebras.ai/) | 采用晶圆级巨大芯片推理，吞吐量和速度处于行业顶尖，永久免费层，支持 Cerebras Code 编程订阅。 |
| **Together AI** | [https://api.together.ai/](https://api.together.ai/) | 著名的开源模型托管与微调平台，涵盖几百款热门开源模型的高效推理，支持自定义微调。 |
| **Anyscale** | [https://app.endpoints.anyscale.com/](https://app.endpoints.anyscale.com/) | 基于 Ray 的大规模模型推理平台，性能稳定，适合分布式 AI 工作流。 |
| **DeepInfra** | [https://deepinfra.com/](https://deepinfra.com/) | 极高性价比的开源模型和语音/图像大模型云 API 平台。 |
| **Fireworks AI** | [https://fireworks.ai/](https://fireworks.ai/) | 提供高速的开源语言模型与多模态模型推理及极速微调服务，新用户赠 $1 额度。 |
| **Replicate** | [https://replicate.com/](https://replicate.com/) | 开源模型（特别是图像、视频、音频扩散模型）的 API 托管重镇，社区生态活跃。 |
| **Nebius** | [https://studio.nebius.com/](https://studio.nebius.com/) | 全球分布式 GPU 算力平台，赠送 $100 免费推理额度，Startup 计划最高 $150K。 |
| **SambaNova Cloud** | [https://cloud.sambanova.ai/](https://cloud.sambanova.ai/) | 自研 RDA 架构的高速推理平台，$5 免费额度，用完后仍有永久免费层（限速）。 |
| **Hyperbolic** | [https://app.hyperbolic.xyz/](https://app.hyperbolic.xyz/) | 去中心化 GPU 算力网络，提供极低成本的开源模型 API 及算力租赁，推荐奖励丰厚。 |
| **Modal** | [https://modal.com/](https://modal.com/) | Serverless GPU 计算平台，按秒计费，每月 $30 免费额度，学术用户最高 $10,000 额度。 |
| **Lepton AI** | [https://www.lepton.ai/](https://www.lepton.ai/) | 高效的 Serverless AI 端点托管平台（现 NVIDIA DGX Cloud Lepton），Basic 免费计划永久可用。 |
| **Hugging Face Endpoints** | [https://huggingface.co/inference-endpoints](https://huggingface.co/inference-endpoints) | 提供专有或无服务器的大量开源模型推理端点，与 HF 开源生态深度绑定。 |
| **Novita AI** | [https://novita.ai/](https://novita.ai/) | 全球大模型 API 及 AI 算力平台，性价比突出，支持图像/视频/语言多种模型。 |
| **Cloudflare Workers AI** | [https://ai.cloudflare.com/](https://ai.cloudflare.com/) | Cloudflare 的轻量级 Serverless 推理平台，在全球边缘节点运行开源模型，延迟极低。 |
| **Lambda (Lambda Labs)** | [https://lambda.ai/](https://lambda.ai/) | 提供 GPU 云基础设施和 OpenAI 兼容的推理 API，以低成本托管主流开源模型著称。 |
| **OVHcloud AI Endpoints** | [https://endpoints.ai.cloud.ovh.net/](https://endpoints.ai.cloud.ovh.net/) | 欧洲云巨头 OVH 的 Serverless 推理服务，支持大量开源权重模型，强调 GDPR 合规和数据主权。 |
| **RunPod** | [https://www.runpod.io/](https://www.runpod.io/) | AI 优先的 GPU 云平台，提供 Serverless GPU Endpoints 和按需 Pod，快速启动和灵活计费。 |
| **CoreWeave** | [https://www.coreweave.com/](https://www.coreweave.com/) | 专业 GPU 云提供商，Kubernetes 原生，面向大规模企业级推理和训练工作负载。 |
| **kluster.ai** | [https://kluster.ai/](https://kluster.ai/) | 专注可扩展推理的平台，支持自适应推理（实时/异步/批处理），OpenAI 兼容 API，成本优化出色。 |
| **BentoCloud** | [https://www.bentoml.com/](https://www.bentoml.com/) | BentoML 的托管推理平台，支持将模型打包为标准化 API，提供高性能容器化推理基础设施。 |
| **OctoAI** | [https://octoai.cloud/](https://octoai.cloud/) | 计算优化的推理平台，帮助开发者以高吞吐低延迟运行和扩展模型。 |
| **DigitalOcean (GenAI)** | [https://www.digitalocean.com/](https://www.digitalocean.com/) | 开发者友好的云平台，已扩展 GPU 集群和托管服务，适合初创团队从实验到生产的 AI 部署。 |
| **Inference.net** | [https://inference.net/](https://inference.net/) | 分布式计算网络的 Serverless 推理平台和网关，支持路由流量到多个下游提供商。 |
| **ShareAI** | [https://shareai.now/](https://shareai.now/) | 市场化模型聚合平台，提供 OpenAI 兼容 API，内置延迟/成本可视化和流量路由。 |
| **NVIDIA NIM** | [https://build.nvidia.com/](https://build.nvidia.com/) | 英伟达官方的推理微服务，提供经过极致优化的各种开源大模型标准 API。 |
| **AkashML** | [https://akash.network/](https://akash.network/) | 去中心化云计算网络 (Akash Network) 上的 AI API 托管服务，具有高性价比算力。 |
| **AtlasCloud** | [https://www.atlascloud.ai/](https://www.atlascloud.ai/) | 云计算和 AI 推理服务提供商，提供高性能的大模型 API。 |
| **Avian** | [https://avian.io/](https://avian.io/) | 面向企业数据分析的 AI 平台和 API，支持连接各类业务数据源。 |
| **BaseTen** | [https://www.baseten.co/](https://www.baseten.co/) | 高性能 AI 模型推理与部署平台，支持极速启动和自动扩展。 |
| **Chutes** | [https://chutes.ai/](https://chutes.ai/) | 专注 AI 模型推理与加速的云服务商。 |
| **Cirrascale** | [https://www.cirrascale.com/](https://www.cirrascale.com/) | 专业的深度学习 GPU 云基础设施提供商，支持大规模 AI 推理集群。 |
| **Crusoe** | [https://crusoe.ai/](https://crusoe.ai/) | 清洁能源驱动的云计算平台，提供环保且具性价比的 GPU 计算及 AI API。 |
| **DekaLLM** | [https://www.cloudeka.id/](https://www.cloudeka.id/) | 印度尼西亚本土云服务商提供的大模型 API 平台，强化东南亚语言支持。 |
| **Featherless** | [https://featherless.ai/](https://featherless.ai/) | 提供各类开源 LLM 推理 API，侧重于无缝的开发者体验和低延迟。 |
| **FriendliAI** | [https://friendli.ai/](https://friendli.ai/) | 极致优化推理引擎 (Friendli Engine)，提供高性能、低延迟的模型 API。 |
| **GMICloud** | [https://www.gmicloud.ai/](https://www.gmicloud.ai/) | 面向全球的 GPU 云服务，提供托管的大模型推理服务端点。 |
| **InceptionLabs** | [https://www.inceptionlabs.ai/](https://www.inceptionlabs.ai/) | 新兴的 AI 推理初创公司，提供特定的模型 API 接入服务。 |
| **Inceptron** | [https://www.inceptron.io/](https://www.inceptron.io/) | 北欧地区 (芬兰节点为主) 的 AI 算力与推理服务。 |
| **InferenceNet** | [https://inference.net/](https://inference.net/) | 去中心化和分布式计算网络的 Serverless 推理平台。 |
| **Infermatic** | [https://infermatic.ai/](https://infermatic.ai/) | 高性价比的开源语言模型推理 API，广受开源开发者欢迎。 |
| **Ionstream** | [https://ionstream.ai/](https://ionstream.ai/) | 高吞吐量 AI 推理与数据流处理平台。 |
| **Mancer** | [https://mancer.tech/](https://mancer.tech/) | 提供未被过度审查 (uncensored) 和角色扮演优化的开源模型 API。 |
| **Mara** | [https://www.mara.com/](https://www.mara.com/) | 专注合规与隐私的云基础设施，提供安全的 AI API 部署。 |
| **ModelRun** | [https://modelrun.org/](https://modelrun.org/) | 支持开发者一键部署与运行 AI 模型的云服务平台。 |
| **Morph Labs** | [https://morphllm.com/](https://morphllm.com/) | 优化的开源大模型云 API 服务。 |
| **NCompass** | [https://ncompass.tech/](https://ncompass.tech/) | 提供端到端的 AI 推理和延迟优化服务接口。 |
| **Parasail** | [https://www.parasail.io/](https://www.parasail.io/) | 去中心化 DePIN 网络的 GPU 算力平台。 |
| **Perceptron** | [https://www.perceptron.inc/](https://www.perceptron.inc/) | AI 基础设施与推理 API 服务提供商。 |
| **Phala Network** | [https://phala.network/](https://phala.network/) | 基于 TEE (可信执行环境) 的去中心化 AI 推理，主打绝对的数据隐私。 |
| **Relace** | [https://www.relace.ai/](https://www.relace.ai/) | 企业级 AI 流程自动化及 API 端点提供商。 |
| **Modular** | [https://www.modular.com/](https://www.modular.com/) | MAX 引擎开发者，提供异构硬件上极速的 AI 模型推理端点。 |
| **Sourceful** | [https://www.sourceful.com/](https://www.sourceful.com/) | 提供稳定的大模型路由与推理服务。 |
| **Venice** | [https://venice.ai/](https://venice.ai/) | 隐私优先的生成式 AI 平台，通过其 API 获取无许可、本地化的开源模型体验。 |
| **Weights & Biases (WandB)** | [https://wandb.ai/](https://wandb.ai/) | MLOps 巨头，其 W&B Serverless 端点为开发者提供可观测的推理 API。 |
| **Z.AI** | [https://chat.z.ai/](https://chat.z.ai/) | 新加坡的 AI 应用与聚合平台，提供各类前沿大模型接口。 |

---

## 三、补充说明

### 本文档覆盖统计

| 分类 | 数量 |
| --- | --- |
| 国内原始大模型厂商 | 29 家 |
| 国内算力/聚合云服务平台 | 16 家 |
| 国外原始大模型厂商 | 27 家 |
| 国外云服务/算力/聚合平台 | 59 家 |
| **合计** | **131 家** |

### 与 README.md 的关系

本文件为**全量数据源/检索底稿**，`README.md` 中 Part 1（白嫖指南 24 家）和 Part 2（编程订阅 7 家）的所有提供商均已完整包含在本列表中。后续将基于本文件进行筛选更新。

### 数据时效性

> ⚠️ 本文档信息基于 2026 年 6 月的公开资料整理，各平台模型版本、定价和服务策略更新频繁，请以官方最新公告为准。
