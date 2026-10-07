# Muse 冷启动一键安装任务

用途：用户将新版天工候选包上传到 Muse 主要聊天后，发送“执行安装”。

执行要求：
1. 不调用旧版天工Skill，不复用旧9窗口结构。
2. 删除/停用旧版天工Skill、测试Skill、tiangong_smoke_test与旧测试聊天；保留即梦/MiniMax等必要登录态和连接授权。
3. 解包后，将包内 runtime/ 内容作为唯一系统本体部署到：
   /home/hatch/workspace/tiangong/
4. 不把 SKILL.md、agents/openai.yaml 注册为 Muse 运行 Skill；这两项若随源码包存在，仅为GitHub兼容/公开发布元数据。
5. 初始化项目目录：
   /home/hatch/workspace/projects/dongbei_xiyouji/
   使用 project_seed/ 中的文件作为初始状态。
6. 校验 references/ 四核心文件SHA与 provenance/SOURCE_REGISTRY.md 一致。
7. 校验 roles/ 7岗位、templates/ 15模板、adapters/ 3适配器、system/CORE_BINDINGS.md、system/MEDIA_SPEC.md 存在。
8. 准备7个固定聊天窗口：
   主要聊天｜总控制片
   剧本叙事
   视觉资产
   导演分镜
   生成工程
   审片质检
   剪辑后期
9. 如果平台不能由主要聊天自动创建/配置Side Chat，不伪造完成；提示用户依次进入7个聊天，并使用 WINDOW_BOOTSTRAP.md 中对应的一次性启动句。
10. 完成安装后只报告：
   INSTALL_STATUS
   system_path
   project_path
   core_hash_check
   roles_count
   templates_count
   adapters_count
   windows_ready
   blockers
11. 不在安装阶段进行付费生成。
12. 安装成功后进入21.27四项快速验收。
