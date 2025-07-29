1.  **生成 JSON 重定向文件**：根据规则（`key` 为 “商汤-” + 服务名称 + [“-免费”]，`value` 为原始服务名称）创建 JSON 对象。
2.  **提取所有 Key**：从生成的 JSON 对象中提取所有的 `key`，并用英文逗号连接。

---

### 1. JSON 重定向文件

```json
{
  "商汤-Qwen3-32B-免费": "Qwen3-32B",
  "商汤-Qwen3-235B-免费": "Qwen3-235B",
  "商汤-SenseNova-V6-Reasoner": "SenseNova-V6-Reasoner",
  "商汤-SenseNova-V6-Turbo": "SenseNova-V6-Turbo",
  "商汤-SenseNova-V6-Pro": "SenseNova-V6-Pro",
  "商汤-SenseChat-5-beta": "SenseChat-5-beta", 
  "商汤-DeepSeek-R1-Distill-Qwen-32B-免费": "DeepSeek-R1-Distill-Qwen-32B",
  "商汤-DeepSeek-R1-Distill-Qwen-14B-免费": "DeepSeek-R1-Distill-Qwen-14B",
  "商汤-DeepSeek-V3-免费": "DeepSeek-V3",
  "商汤-DeepSeek-R1-免费": "DeepSeek-R1",
  "商汤-SenseChat-5-1202": "SenseChat-5-1202",
  "商汤-SenseChat-Turbo-1202": "SenseChat-Turbo-1202",
  "商汤-Llama3-8B-免费": "Llama3-8B",
  "商汤-Llama3-70B-免费": "Llama3-70B",
  "商汤-Qwen2-7B-免费": "Qwen2-7B",
  "商汤-Qwen2-72B-免费": "Qwen2-72B",
  "商汤-nova-tts-1-免费": "nova-tts-1",
  "商汤-SenseChat-Vision": "SenseChat-Vision",
  "商汤-SenseChat-Character-Pro": "SenseChat-Character-Pro",
  "商汤-SenseChat-5-Cantonese": "SenseChat-5-Cantonese",
  "商汤-SenseChat-5": "SenseChat-5",
  "商汤-SenseChat-Character": "SenseChat-Character",
  "商汤-nova-embedding-stable": "nova-embedding-stable",
  "商汤-SenseChat-128K": "SenseChat-128K",
  "商汤-SenseChat-Turbo": "SenseChat-Turbo",
  "商汤-SenseChat": "SenseChat",
  "商汤-SenseChat-32K": "SenseChat-32K",
  "商汤-online_search_count-免费": "online_search_count"
}
```

### 2. 提取的所有 Key (英文逗号分隔)

```
商汤-Qwen3-32B-免费,商汤-Qwen3-235B-免费,商汤-SenseNova-V6-Reasoner,商汤-SenseNova-V6-Turbo,商汤-SenseNova-V6-Pro,商汤-SenseChat-5-beta,商汤-DeepSeek-R1-Distill-Qwen-32B-免费,商汤-DeepSeek-R1-Distill-Qwen-14B-免费,商汤-DeepSeek-V3-免费,商汤-DeepSeek-R1-免费,商汤-SenseChat-5-1202,商汤-SenseChat-Turbo-1202,商汤-Llama3-8B-免费,商汤-Llama3-70B-免费,商汤-Qwen2-7B-免费,商汤-Qwen2-72B-免费,商汤-nova-tts-1-免费,商汤-SenseChat-Vision,商汤-SenseChat-Character-Pro,商汤-SenseChat-5-Cantonese,商汤-SenseChat-5,商汤-SenseChat-Character,商汤-nova-embedding-stable,商汤-SenseChat-128K,商汤-SenseChat-Turbo,商汤-SenseChat,商汤-SenseChat-32K,商汤-online_search_count-免费
```