# FreeLLM-API-KeyHub 🆓

实时追踪大模型平台免费资源 | [English](README_EN.md) | [更新日志](#更新日志) | [提交情报](CONTRIBUTING.md)

[![自动校验](https://github.com/yourname/FreeLLM-Resources/actions/workflows/validate.yml/badge.svg)](https://github.com/yourname/FreeLLM-Resources/actions)
[![最后更新](https://img.shields.io/badge/最后更新-2024.03.15-blue)](https://github.com/yourname/FreeLLM-Resources/commits/main)

## 🔥 热门推荐
平台 | 免费额度 | 有效期 | 亮点 | 状态
--- | --- | --- | --- | ---
**商汤DeepSeek** | 1000万Token | 至2024-05-09 | R1/V3双模型 | 🚨 即将到期
**腾讯混元** | 100万Token | 至2025-02-25 | 长期稳定 | ✅ 推荐
**讯飞星辰** | 未注明 | 至2025-03-10 | 支持建议反馈 | 🆕 新平台

## 📋 全平台速查表
平台 | 类型 | 免费额度 | 有效期 | 限制条件 | 文档链接
--- | --- | --- | --- | --- | ---
天翼云 | 云服务 | 2500万 | 2周 | 企业认证 | [指南](https://www.ctyun.cn/act/xirang/deepseek)
移动云 | 云服务 | 2500万 | 30天 | 低使用量 | [文档](https://ecloud.10086.cn/portal/act/deepseek)
华为云 | 云服务 | 200万/模型 | 长期 | 独立接口 | [API文档](https://activity.huaweicloud.com/maas-ds.html)
阿里百炼 | 平台 | 100万/模型 | 30-180天 | 模型差异 | [控制台](https://bailian.console.aliyun.com/)
商汤 | AI Studio | 1000万 | 至2024-05-09 | 切换地区 | [资源中心](https://console.sensecore.cn/aistudio)
火山引擎 | 云服务 | 50万 | 未注明 | 高速通道 | [接入指南](https://www.volcengine.com/product/ark)
英伟达 | 开发者 | 1000次 | 长期 | 新用户 | [申请入口](https://build.nvidia.com/explore/discover)

## 🚨 DeepSeek专项
### 限免信息
平台 | 模型版本 | 截止日期 | 调用地址
--- | --- | --- | ---
商汤 | R1/V3 | 2024-05-09 | `api.sensetime.com/v1/chat/completions`
讯飞 | R1/V3 | 2025-03-10 | `training.xfyun.cn/api/v1/invoke`

```python
# 基础调用示例
import requests
response = requests.post(
    "API_ENDPOINT",
    headers={"Authorization": "Bearer YOUR_KEY"},
    json={"model": "deepseek-r1", "messages": [...]}
)
