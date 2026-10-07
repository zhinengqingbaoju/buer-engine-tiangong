# KNOWN_LIMITATIONS
版本：v01_20261008

1. Muse原生视频画面理解可用，但测试入口无法直接理解音频内容；无外接STT/可听模型/用户试听时，audio QA必须标NOT_VERIFIED。
2. Seedance 2.5官方能力与即梦/Muse当前UI能力分开；参考上传、具体视频模式和部分UI参数需21.27/真实生产继续核验。
3. MiniMax H3/Hailuo 2.3必须先读取当前实际入口型号；不得跨型号套能力。
4. Muse跨聊天当前可靠模式仍是：总控写Task→用户进入目标窗口发“执行待办”→共享状态读写。
5. 当前项目current_focus_object需MIG-001安装后迁移审计，不从历史聊天猜。
6. 多个已锁定人物资产的高强度跨姿态/跨光照/同框压力测试仍未完成；locked不等于stress-tested。
7. HELL GRIND Team Guide、官方11-stage、Illustrated Handbook/Slop Gallery等原件仍MISSING；当前11阶段明确为不二引擎重建版。
8. 候选包尚未通过21.28/21.30真实镜头和21.32六路Muse Agent终审，因此不是稳定版。
