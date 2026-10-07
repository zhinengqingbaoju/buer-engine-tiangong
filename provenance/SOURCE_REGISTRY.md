# SOURCE REGISTRY｜来源登记册
版本：v01_20261008

字段：SOURCE_ID｜名称｜类别｜版本/日期｜权威等级｜状态｜适用模块｜链接/哈希｜备注

权威等级：
L0 用户最新明确决定 / 已确认项目事实
L1 四份天工核心原文
L2 当前官方文档 / 平台真实实测
L3 HELL GRIND真实生产档案 / 项目真实案例
L4 成熟影视工业标准 / 专业软件官方结构
L5 历史研究 / 第三方重建 / 社区经验

## A｜用户与《东北西游记》项目事实
A-001｜项目当前明确指令与已批准创作决定｜持续更新｜L0｜ACTIVE｜全系统｜项目记录｜最高项目事实
A-002｜东北西游记项目指南.md｜v01_20261005｜L0/L3｜ACTIVE_REFERENCE｜项目导航｜Library｜不是四核心原文替代物
A-003｜东北西游记_锁定资产清单与归档规则_v15_20261008.md｜v15｜L0｜ACTIVE_CANONICAL｜资产/状态/归档｜https://drive.google.com/file/d/1b2PYRiBPja1HGWMHiwKsmDSYqhbpF7_j/view?usp=drivesdk｜当前锁定资产Source of Truth
A-004｜AI短视频通用图片资产尺寸与比例标准_v01_20261007｜v01｜L0｜ACTIVE_HARD_SPEC｜视觉资产/关键帧/交付｜system/MEDIA_SPEC.md｜完整逐字收录，不以摘要替代
A-005｜AI短视频通用视频资产执行标准_v01_20261007｜v01｜L0/L3｜ACTIVE_REFERENCE｜生成/QA/返修｜项目文件｜逐字段以核心/实测核验
A-006｜当前锁定人物/场景/道具真实资产与Drive链接｜持续更新｜L0/L3｜ACTIVE_MEDIA｜资产/镜头/生成｜v15清单与Drive｜真实媒体事实源
A-007｜Muse实机联调结果｜2026-10-07｜L2/L3｜ACTIVE｜Runtime/权限/状态/媒体理解｜20/20A报告｜实测优先于假设
A-008｜7窗口批准决定｜2026-10-07｜L0｜ACTIVE｜Muse岗位架构｜项目决定｜覆盖旧9窗口
A-009｜总指挥Agent小范围路线授权｜2026-10-07｜L0｜ACTIVE｜系统治理｜项目决定
A-010｜最终六路独立审查要求｜2026-10-07｜L0｜ACTIVE｜最终发布门｜项目决定
A-011｜天工不作为Muse额外运行Skill；四核心直接绑定岗位｜2026-10-08｜L0｜ACTIVE｜架构/Runtime｜用户明确决定｜覆盖此前“运行Skill路由”方案

## B｜四份核心与仓库实现
B-001｜zhinengqingbaoju/buer-engine-tiangong｜RC branch｜L2/L3｜DEVELOPMENT_SOURCE｜版本源｜GitHub｜不作为Muse运行依赖
B-002｜SKILL.md｜RC兼容索引｜L5/IMPLEMENTATION｜COMPAT_INDEX_ONLY｜未来公开发布/兼容｜仓库｜Muse冷启动包不注册为运行Skill
B-003｜PROJECT_BRIEF.md｜SHA b783cda5c7e8e6799f366d69c5202c64c8896082｜L1｜ACTIVE_CORE｜总则/资产/空间/制作/返修/后期
B-004｜LIRA SKILL.md｜SHA 1e5c80731d5f6ccd0d2e803678598da42ce835e7｜L1｜ACTIVE_CORE｜图片资产/编辑/身份/材质
B-005｜ACTING SKILL.md｜SHA 383db473e88e70a2e3ed30f962e4ea56da5a645b｜L1｜ACTIVE_CORE｜表演/行为/声音
B-006｜CINEDANCE HIGGSFIELD SKILL.md｜SHA 24d38044ae06e5159cf5662b2bf5e09164789894｜L1｜ACTIVE_CORE｜导演/镜头/摄影/视频Prompt/物理/声音
B-007｜agents/openai.yaml｜RC元数据｜L5/IMPLEMENTATION｜PUBLICATION_METADATA_ONLY｜公开发布兼容｜Muse包不启用implicit invocation

## C｜HELL GRIND真实生产证据
C-001｜XucroYuri/higgsfield-hell-grind-opensource｜master；关键研究固定79c8d13...｜L3｜ACTIVE_EVIDENCE｜全系统研究｜GitHub公开镜像
C-002｜HELL GRIND全库盘点｜v01_20261007｜L3｜ACTIVE_RESEARCH｜Prompt/Generation/结构
C-003｜HELL GRIND真实迭代与Regenerations研究｜v01_20261007｜L3｜ACTIVE_RESEARCH｜返修/Prompt迭代
C-004｜HELL GRIND失败返修案例库｜v01_20261007｜L3｜ACTIVE_RESEARCH｜QA/Repair
C-005｜Team Guide｜未知｜L1潜在｜MISSING｜运行指南｜不得冒充已取得
C-006｜官方11-stage pipeline｜未知｜L1潜在｜MISSING｜流程｜当前使用“不二引擎重建版”
C-007｜Illustrated Handbook / Slop Gallery｜未知｜L1潜在｜MISSING｜QA视觉案例
C-008｜shotlists/screenplay/asset registry/workbench｜未知｜L3潜在｜MISSING_PARTIAL｜仅使用已核实片段

## D｜当前模型官方与平台实测
D-001｜OpenAI Images 2.5 / GPT Image 2.5｜2026-09-08起｜L2｜ACTIVE_CURRENT｜GPT图片Adapter｜OpenAI官方
D-002｜OpenAI Image generation / prompting docs｜2026-10-08核验｜L2｜ACTIVE_CURRENT｜GPT参数/编辑/输入输出｜developers.openai.com
D-003｜ByteDance Seedance 2.5发布与产品页｜2026-07-31；2026-10-08核验｜L2｜ACTIVE_CURRENT｜Seedance能力｜seed.bytedance.com
D-004｜BytePlus Seedance 2.5 Prompt Guide｜当前｜L2｜ACTIVE_CURRENT｜Seedance Prompt结构｜docs.byteplus.com
D-005｜MiniMax H3官方发布/开源说明｜2026-07-31/08-03；2026-10-08核验｜L2｜ACTIVE_CURRENT｜MiniMax H3
D-006｜MiniMax Hailuo 2.3官方发布｜2025-10-28｜L2｜ACTIVE_MODEL_FALLBACK｜Hailuo路线
D-007｜Muse即梦Seedance干跑｜2026-10-07｜L2/L3｜PARTIAL_PASS｜平台入口｜参考上传/视频专属参数未完全验证
D-008｜Muse MiniMax干跑｜2026-10-07｜L2/L3｜PASS_DRYRUN｜平台入口｜实际型号仍需识别
D-009｜Muse视频视觉/音频QA实测｜2026-10-07｜L2/L3｜VIDEO_PASS_AUDIO_FAIL｜QA｜未外接音频路径不得宣称完整声画通过

## E｜传统影视工业样板
E-001｜Celtx Breakdown｜L4｜ACTIVE_REFERENCE｜剧本拆解/Scene↔Asset
E-002｜Celtx Catalog｜L4｜ACTIVE_REFERENCE｜资产登记
E-003｜Celtx Shot Lists｜L4｜ACTIVE_REFERENCE｜镜头字段
E-004｜StudioBinder Shot List｜L4｜ACTIVE_REFERENCE｜Shot/angle/movement/lens
E-005｜OpenTimelineIO｜L4｜ACTIVE_REFERENCE｜Timeline/Track/Clip/Transition/Marker
原则：只借成熟对象/字段边界，不机械照搬实拍行政/器材字段。

## F｜历史与第三方
F-001～F-007｜旧AI短剧总手册+六专业系统｜L5/L3｜REFERENCE_ONLY｜字段/历史经验｜不得平行复活
F-008｜中文版执行手册｜L5｜TEACHING_REFERENCE｜教学
F-009｜六文件红军审核报告｜L5/L3｜AUDIT_REFERENCE｜审查方式/历史缺陷
F-010｜drama-skills研究｜L5｜REFERENCE_ONLY｜模型方言/检查器
F-011｜天工增补/11阶段/运行指南/QA/架构/状态/适配器/Muse联调研究｜L3｜DESIGN_EVIDENCE｜重构证据｜以当前RC正式文件为执行权威

唯一性：
L0项目事实 > 宪法 > L1对应专业原文 > L2当前官方/实测 > L3真实生产证据 > L4工业样板 > L5历史/第三方。
