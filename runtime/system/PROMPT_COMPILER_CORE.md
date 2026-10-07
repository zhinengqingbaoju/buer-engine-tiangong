# 模型无关 Prompt 编译核心
版本：v01_20261007

Prompt是编译产物，不是事实源。

Task Contract输入：object_id,task_type,approved_visual_facts,approved_dialogue,active_asset_versions,reference_roles,GEO/blocking,camera_contract,action_beats,audio_requirements,preserve_requirements,failure_history,output_goal

Master Prompt槽位：
1 TASK/GOAL
2 ACTIVE ASSETS & REFERENCE ROLES
3 SCENE/GEO/BLOCKING
4 OPENING STATE
5 CAMERA CONTRACT
6 TIMELINE/ACTION BEATS
7 PERFORMANCE
8 PHYSICS/MATERIAL BEHAVIOR
9 DIALOGUE VERBATIM
10 AUDIO REQUIREMENTS
11 ENDING STATE
12 PRESERVE
13 DO-NOT-CHANGE/HARD CONSTRAINTS
14 OUTPUT SPEC
15 KNOWN RISKS/FAILURE HISTORY

规则：只取approved/active事实；中文对白逐字；reference写继承什么，必要时写不继承什么；不支持要求进入unsupported；适配器可重排/压缩但不能改事实；旧Prompt引用失效上游则STALE。

图片：NEW / EDIT(CHANGE+PRESERVE) / REBUILD。
视频：先由Adapter确认真实可用模式，再编译。
输出：master_prompt_version,target_adapter,target_prompt,reference_map,platform_settings,unsupported_requirements,assumptions,preflight_status。
