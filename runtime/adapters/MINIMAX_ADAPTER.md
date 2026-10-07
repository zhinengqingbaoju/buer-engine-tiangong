# MINIMAX ADAPTER
版本：v01_20261008｜第二视频路线

## MiniMax H3 官方能力
官方2026-07-31发布、2026-08-03开源说明：
- 统一理解 text / image / video / audio
- 原生32 kHz stereo audio
- 输出4–15秒
- 24 FPS
- 最高2K（官方系统含H3-Regenerate-2K；实际Muse UI是否暴露2K必须单独验证）
- FL2VA：0/1/2图，可T2V、首帧、尾帧、首尾帧
- Ref2VA官方输入：≤9 images、≤3 videos、≤3 audios；混合文件总数≤12；音频不能作为唯一输入，需配图/视频
- 官方强调instruction following、text/brand rendering、V2V motion transfer

来源：
https://www.minimax.io/blog/minimax-h3
https://www.minimax.io/news/minimax-h3-open-source

## Hailuo 2.3
官方2025-10-28：
复杂人体动作、物理、微表情、动态镜头与运动指令响应提升。
来源：
https://www.minimax.io/news/minimax-hailuo-23

## 硬规则
actual_model 必须从当前入口真实识别：
H3 / Hailuo 2.3 / Hailuo 02 / other / UNKNOWN。
UNKNOWN时不编译型号专属能力。

Muse海螺浏览器干跑：
- 进入创作面板 PASS
- Prompt填写 PASS
- 到最终提交按钮前 PASS
- reference upload自动化 NOT_VERIFIED
- actual model variant NEED_DETECTION

官方能力 ≠ Muse UI能力；时长、2K、首尾帧、多参考、音频、V2V都必须按当前入口标AVAILABLE_UI或NOT_VERIFIED。

## 跨模型切换
从Seedance切MiniMax时保持：
对白、资产身份、GEO、镜头意义、动作目的、表演目的、首尾状态。

只重新编译：
reference mapping、Prompt外层、mode、duration/resolution、audio input、platform settings。

A/B测试必须使用同一Shot Contract、批准资产、动作目标与对白。
