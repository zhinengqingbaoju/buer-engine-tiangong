# SEEDANCE 2.5 ADAPTER
版本：v01_20261008｜当前主视频路线

## 官方当前基线
ByteDance Seed 2026-07-31发布 Seedance 2.5：
- 单次最高30秒
- 多模态参考：官方发布页明确最多30张图片、10段视频、10段音频
- 音视频联合生成
- timestamp级控制/编辑
- 更强参考、镜头、blocking与物理控制
- 支持视频延长；官方发布文章表述为multi-round extensions，当前产品页写“extend twice”，因此实际可延长次数以当前入口为准，不假设无限多轮

来源：
https://seed.bytedance.com/en/blog/one-take-creation-flexible-referencing-introducing-seedance-2-5
https://seed.bytedance.com/en/seedance2_5
BytePlus/Dreamina Seedance 2.5 Prompt Guide

## 平台隔离
官方模型能力 ≠ 即梦网页UI ≠ Muse浏览器自动化能力。

当前Muse实测：
- 即梦登录/统一创作入口可达
- Seedance 2.5入口存在
- Prompt可填写
- 可停在生成按钮前且零消耗
- 视频模式参考上传、时长、具体生成模式未完整验证

因此：
model_capability 与 ui_capability 分开记录。
未实测UI字段 = EXPERIMENTAL / NOT_VERIFIED。

## 先识别实际模式
T2V / first-frame / first-last / reference / video-ref / audio-ref / edit / extend / other。
只有当前UI真实存在才标 AVAILABLE_UI。

## Reference Contract
每个素材：
reference_id
upload_order
role
inherit
do_not_inherit

角色可包括：
identity / outfit-state / location-geography / prop / start-frame / end-frame / motion / video / voice-audio / style-material / clay-structure

## Prompt外层
按当前官方Prompt Guide可采用：
1 Asset Referencing
2 One-Sentence Summary
3 Detailed Plot（timestamps或Shot N）
4 Additional Notes

外层属于Seedance适配器；Master Prompt内部事实结构不随模型改变。

## 中文对白
批准中文对白逐字保留中文；角色、时点、OS/VO需要时明确。
不得为模型流畅度自行改词。

## 30秒原则
30秒是模型能力上限，不是镜头目标。高风险多人交互、复杂物理、密集对白是否拆镜由导演分镜决定。

## Preflight
actual_mode verified
references actually mounted
reference roles clear
asset versions current
subject/prop counts
dialogue verbatim
duration/ratio supported in current UI
audio requirement compatible
no stale refs
no phantom @tag
authorization

失败：
随机→reroll；稳定执行偏差→minimal rewrite；结构过载→director redesign；参考未挂载→input fix；UI不支持→unsupported/换模式。
