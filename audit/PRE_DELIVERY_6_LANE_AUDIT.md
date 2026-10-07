# PRE_DELIVERY_6_LANE_AUDIT
版本：v01_20261008
状态：PRE_DELIVERY_PASS
对象：Muse冷启动候选包

说明：本轮在ChatGPT构建环境进行六路隔离审查轨；当前环境没有Muse真实Subagent接口，因此不冒充“6个Muse Agent”。最终21.32仍要求在Muse使用真实至少6路独立Agent终审。

## Lane 1｜架构/宪法
发现并修复：
- Muse不再安装/调用额外“天工运行Skill”
- 四核心直接绑定7岗位
- Controller去掉Skill调用
- openai.yaml禁用implicit invocation
结果：PASS

## Lane 2｜包体/Runtime
发现并修复：
- 单一系统路径 /home/hatch/workspace/tiangong/
- 新增ONE_CLICK_INSTALL
- 新增7窗口WINDOW_BOOTSTRAP
- 新增project_seed实际状态文件
- 新增PARALLEL_EXECUTION
结果：PASS_PENDING_MUSE_INSTALL

## Lane 3｜数据/状态/权限
发现并修复：
- current_stage改为当前焦点对象阶段语义
- 增加Script对象、SCRIPT_REGISTRY、GEO_REGISTRY
- Asset状态统一adopted术语
- Task增加waiting_user/waiting_authorization
- QA支持ISSUES[]多问题
结果：PASS

## Lane 4｜模板/Prompt/媒体规格
发现并修复：
- 完整加入用户MEDIA_SPEC：人物3:4、道具4:3、横向综合16:9、材质1:1、竖屏关键帧9:16、横屏关键帧16:9、最终1080×1920/1920×1080
- T09增加REFERENCE MAP
- T10拆prompt_id/prompt_version
- GEO改allowed_camera_sides
- Project Brief去除动态current_stage
结果：PASS

## Lane 5｜模型适配/来源时效
2026-10-08重新核验官方：
- OpenAI GPT Image 2.5 Flare/Sunburst
- Seedance 2.5：30秒、30图/10视频/10音频、timestamp控制；延长次数以当前入口为准
- MiniMax H3：4–15秒、24FPS、32kHz stereo、最高2K系统、FL2VA/Ref2VA输入边界
- Hailuo 2.3单独分支
结果：PASS_MODEL_DOCS
Muse UI未实测能力继续标NOT_VERIFIED/EXPERIMENTAL。

## Lane 6｜红队/项目真相/用户操作
重大发现：
原初始化包仍引用v09/38张锁定资产；实际canonical Drive文件已经更新到：
东北西游记_锁定资产清单与归档规则_v15_20261008.md
共40张锁定原图，新增统一麻将双龙纹背面正视图02等当前事实。
已修复：
- Init/Asset Registry/Task/Installer/Source Registry全部切到v15
- 包内保存v15源文件快照
- 用户日常无需启动天工Skill
- 生产并行按任务可分性使用Muse临时Agent，不机械固定6路
结果：PASS_WITH_KNOWN_LIMITATIONS

## 当前非包体阻断
- 21.26 Muse真实解包/落盘/7窗口初始化
- 21.27四项快速验收
- Seedance/MiniMax实际UI进一步验证
- Muse原生音频QA缺口
- MIG-001当前项目生产焦点迁移
- 21.28/21.30两类真实镜头验证
- 21.32 Muse真实6路Agent终审

结论：候选包可交付用于21.26，不得称最终稳定版。
