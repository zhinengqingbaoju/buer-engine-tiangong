# FIELD PROVENANCE MATRIX｜字段—来源—证据矩阵
版本：v01_20261008

说明：正式数据字段与运行模板不得无来源生长。M=必填；O=选填。

## Governance
F-GOV-001 approved_by｜Decision/Script/Selection｜L0用户控制权｜M when approved｜用户/系统记录
F-GOV-002 approved_at｜Decision/Script/Selection｜L0/L3审计需要｜M when approved
F-GOV-003 locked/status｜Asset/Shot/Selection｜L0用户锁定纪律｜M
F-GOV-004 replaces/supersedes｜Decision/Script/Asset/Selection｜L0/L3版本替代｜O
F-GOV-005 do_not_change｜Task/Shot/Asset｜L0锁定纪律｜M when locked

## Project State
F-STATE-001 current_focus_object｜Project｜L3多对象并行生产现实｜M
F-STATE-002 current_stage｜Project｜11阶段+状态规范｜M｜解释为焦点对象阶段，不是全项目唯一阶段
F-STATE-003 current_episode/scene/shot｜Project｜L3续作恢复｜O
F-STATE-004 active_*_version｜Project｜L3版本治理｜M
F-STATE-005 unresolved_decisions / blocked_items｜Project｜L3项目治理｜O
F-STATE-006 last_completed_action / next_action / next_role｜Project｜L2/L3 Muse移动端接续｜M

## Decision
F-DEC-001 decision_id/category/content｜Decision｜L0/L3｜M
F-DEC-002 status proposed/discussed/approved/superseded｜Decision｜L3｜M
F-DEC-003 impact_scope｜Decision｜L3依赖传播｜O

## Script / Scene
F-SCR-001 script_id/version/status｜Script｜L3版本治理+剧本工业实践｜M
F-SCR-002 scene_ids｜Script｜L4剧本结构｜M
F-SCR-003 locked_dialogue_refs｜Script｜L0对白控制权｜O
F-SC-001 scene_id/script_version｜Scene｜L4/L3｜M
F-SC-002 location_asset_version / character_states / prop_states｜Scene｜L1/L3连续性｜M when applicable
F-SC-003 continuity_in/out｜Scene｜PROJECT_BRIEF/CINEDANCE｜L1｜M

## Asset
F-AS-001 asset_id/name/category｜Asset｜PROJECT_BRIEF + Celtx Catalog/Breakdown｜L1/L4｜M
F-AS-002 base_identity_id/state_version｜Asset｜PROJECT_BRIEF/项目实践｜L1/L3｜O/M
F-AS-003 canonical_descriptor｜Asset｜PROJECT_BRIEF固定描述纪律｜L1｜M when applicable
F-AS-004 actual_media_refs/drive_urls｜Asset｜项目Drive纪律+Celtx media｜L0/L4｜M when media exists
F-AS-005 reference_roles/do_not_inherit｜AssetRef｜LIRA/Seedance官方/项目实战｜L1/L2/L3｜M/O
F-AS-006 status planned/candidate/testing/adopted/locked/deprecated｜Asset｜L0/L3｜M
F-AS-007 test_scope/passed/untested/known_defects｜Asset｜PROJECT_BRIEF压力测试+QA｜L1/L3｜O

## GEO
F-GEO-001 geo_id/version｜GEO｜L3版本治理｜M
F-GEO-002 landmarks/spatial_relations｜GEO｜PROJECT_BRIEF/CINEDANCE｜L1｜M
F-GEO-003 entrances/exits/screen_directions/axis_180｜GEO｜L1/L4连续性｜O/M by scene
F-GEO-004 allowed_camera_sides｜GEO｜电影轴线/项目blocking实践｜L4/L3｜O
F-GEO-005 main_light_direction/restricted_zones｜GEO｜PROJECT_BRIEF/CINEDANCE｜L1｜O

## Shot
F-SH-001 shot_id/scene_id｜Shot｜Celtx/StudioBinder/项目镜号｜L4/L3｜M
F-SH-002 narrative_function/duration_target｜Shot｜CINEDANCE/分镜逻辑｜L1｜M
F-SH-003 shot_size/camera_angle/movement/lens_intent/framing/composition｜Shot｜Celtx/StudioBinder+CINEDANCE｜L4/L1｜O/M by shot
F-SH-004 opening_state/closing_state｜Shot｜AI连续性实践｜L3｜M
F-SH-005 asset_versions/geo_version｜Shot｜依赖传播｜L3｜M
F-SH-006 action_beats/performance｜Shot｜ACTING/CINEDANCE｜L1｜M
F-SH-007 dialogue_verbatim｜Shot｜L0中文对白控制｜O
F-SH-008 audio_requirements/reference_needs/risk_focus｜Shot｜CINEDANCE/Adapter/QA案例｜L1/L2/L3｜O

## Prompt / Adapter
F-PR-001 prompt_id/version/parent_prompt_version｜Prompt｜HELL GRIND链路+状态规范｜L3｜M
F-PR-002 target_model/adapter_version｜Prompt｜L2/L3适配架构｜M
F-PR-003 actual_text/reference_mapping/platform_settings｜Prompt｜L2/L3｜M
F-PR-004 changed_variables/change_reason｜Prompt｜HELL GRIND Regenerations｜L3｜O after v1
F-PR-005 source_versions｜Prompt｜L3防止stale｜M
F-PR-006 unsupported_requirements/assumptions｜Adapter output｜L2/L3防静默删要求/补猜｜O

## Generation
F-GEN-001 generation_id/object_id/prompt_id/version｜Generation｜HELL GRIND元数据+状态规范｜L3｜M
F-GEN-002 model/model_version/adapter_version/mode｜Generation｜L2当前平台｜M when known
F-GEN-003 actual_references/actual_parameters｜Generation｜真实提交证据｜L2/L3｜M/O
F-GEN-004 send_status/provider_status/timestamps/error｜Generation｜Muse实测/可靠审计｜L2/L3｜M
F-GEN-005 result_file/drive_url｜Generation｜L0 Drive交付｜M for image result；其他按项目
F-GEN-006 reroll_index｜Generation｜HELL GRIND迭代｜L3｜O
F-GEN-007 cost_or_credits/cost_evidence｜Generation｜L0额度控制+平台证据｜O

## QA / Repair
F-QA-001 expected/observed/evidence_location｜Issue｜Shot/Asset合同+真实媒体｜L1/L3｜M
F-QA-002 severity S1-S4｜Issue｜QA手册/项目实践｜L3｜M
F-QA-003 responsibility_layer/root_cause_status/recommended_route｜Issue｜责任路由/防猜根因｜L3｜M
F-QA-004 ISSUES[]｜QA｜真实媒体可能多缺陷｜L3｜M when fail
F-REP-001 route reroll/rewrite/asset/geography/redesign/post｜Repair｜HELL GRIND真实迭代｜L3｜M
F-REP-002 changed_variables/preserve_requirements｜Repair｜LIRA/CINEDANCE返修+项目实践｜L1/L3｜M
F-REP-003 retest_result/regression_result｜Repair｜回归要求｜L3｜M

## Selection
F-SEL-001 status candidate/rejected/adopted/locked/replaced｜Selection｜L0用户纪律｜M
F-SEL-002 user_confirmation/known_defects/downstream_usage｜Selection｜L0/L3｜M/O

## Task
F-TASK-001 task_id/target_object/stage/target_role/goal｜Task｜Muse跨窗任务链｜L2/L3｜M
F-TASK-002 required_inputs/preserve_requirements/permissions｜Task｜岗位边界/返修纪律｜L0/L3｜O/M
F-TASK-003 status queued/ready/in_progress/waiting_user/waiting_authorization/blocked/done｜Task｜实际协作状态｜L2/L3｜M
F-TASK-004 blocked_reason/result_refs｜Task｜可恢复执行｜L3｜O

## Edit
F-ED-001 edit_id/version/timeline/tracks｜Edit｜OpenTimelineIO+项目剪辑｜L4/L3｜M
F-ED-002 clip_generation_id/source_range/in_out｜Edit｜OTIO外部媒体引用｜L4/L3｜M
F-ED-003 markers/transitions/audio/subtitle/color/cleanup/vfx｜Edit｜OTIO+项目后期｜L4/L3｜O
F-ED-004 final_export/review_status/full_playback/full_audio_check｜Edit｜L0/L3交付｜M when final

## Media Spec
F-MED-001 image_asset_type/aspect_ratio/pixel_dimensions｜MediaSpec｜用户上传尺寸标准｜L0｜M
F-MED-002 material/texture 1:1 2048×2048｜MediaSpec｜L0｜M when type applies
F-MED-003 vertical keyframe 9:16 1152×2048｜MediaSpec｜L0｜M when type applies
F-MED-004 horizontal keyframe 16:9 2048×1152｜MediaSpec｜L0｜M when type applies
F-MED-005 final vertical 1080×1920 / horizontal 1920×1080｜Delivery｜L0｜M when final
完整定义见 system/MEDIA_SPEC.md。

规则：新增运行字段前，必须先为其补充来源、等级和写权限；不能让模板先于来源矩阵生长。
