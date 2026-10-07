# SEEDANCE 2.5 ADAPTER
版本：v01_20261007｜当前主视频路线

官方基线：2026-07-31发布；最高30秒、多轮extension、多模态reference、音视频联合生成。BytePlus Prompt Guide推荐：Asset Referencing / One-Sentence Summary / Detailed Plot(timestamps或Shot N) / Additional Notes；明确素材上传顺序与用途。
来源：https://seed.bytedance.com/en/blog/one-take-creation-flexible-referencing-introducing-seedance-2-5
https://docs.byteplus.com/ko/docs/modelark/seedance-2-5-prompt-guide?redirect=1

官方能力 ≠ 即梦UI ≠ Muse浏览器能力。
Muse实测：登录/入口/提示词/到生成按钮前PASS；视频模式参考上传、时长、具体模式未完整验证。

先识别actual_mode：T2V/first-frame/first-last/reference/video-ref/audio-ref/edit/extend/other；UI真实存在才AVAILABLE_UI。
Reference Contract：upload_order、role、inherit、do_not_inherit；角色可为identity/outfit/location/prop/start/end/motion/video/voice/style/clay。
中文对白逐字保留；模型能力有音频≠Muse QA能听懂。
30秒是能力上限，不是镜头目标。
Preflight：mode、reference mounted、roles、asset versions、counts、dialogue、duration/ratio/audio、stale refs、phantom @tag、authorization。
