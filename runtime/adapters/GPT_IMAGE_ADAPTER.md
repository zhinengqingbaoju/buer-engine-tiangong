# GPT IMAGE ADAPTER
版本：v01_20261007｜静态图像主适配器

当前官方基线：ChatGPT Images 2.5（2026-09-08）；API含 gpt-image-2.5-flare / gpt-image-2.5-sunburst。官方Image guide：Sunburst偏精确编辑，Flare偏快速高质量生成。
来源：https://openai.com/index/introducing-chatgpt-images-2-5/
https://developers.openai.com/api/docs/guides/tools-image-generation

API ≠ ChatGPT UI ≠ Muse UI；记录surface，不伪造model_variant。
模式：NEW / EDIT / REBUILD。
EDIT固定：SOURCE / CHANGE / PRESERVE / REFERENCE MAP / DO NOT / OUTPUT SPEC；一轮优先一个主问题，结果仍需QA。
多参考必须标 identity/outfit/prop/location/style/structure/composition 及必要的do_not_inherit。
图片规格按用户标准。
待验证：Muse是否可选Flare/Sunburst、Muse多参考与透明背景参数。
