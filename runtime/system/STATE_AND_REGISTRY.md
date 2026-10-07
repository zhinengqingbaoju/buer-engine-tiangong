# PROJECT_STATE 与登记册
版本：v01_20261008

## 1｜存储分层
1. PROJECT_STATE：当前焦点与摘要，保持短。
2. Registries：当前正式事实。
3. Records：历史事件/产物。
4. Media：真实媒体在 Google Drive / 平台，状态只保存引用。

## 2｜PROJECT_STATE
project_id
project_name
current_focus_object
current_stage
current_episode
current_scene
current_shot
active_script_version
active_visual_direction_version
active_pipeline_version
active_role_schema_version
active_adapter_versions
active_asset_set
open_issue_count
unresolved_decisions
blocked_items
last_completed_action
next_action
next_role
updated_at

说明：
current_stage 是 current_focus_object 的阶段，不代表整个项目只有一个全局阶段。不同场次、镜头、资产可并行处于不同生产状态。

## 3｜Registries
DECISION_REGISTRY
SCRIPT_REGISTRY
ASSET_REGISTRY
SCENE_REGISTRY
GEO_REGISTRY
SHOT_REGISTRY
TASK_QUEUE

## 4｜Records
PROMPT_RECORDS
GENERATION_RECORDS
ISSUE_RECORDS
REPAIR_RECORDS
SELECTION_RECORDS
EDIT_RECORDS
ROUTE_CHANGE_LOG

## 5｜原则
- 聊天不是事实源。
- active版本显式记录。
- 历史版本保留。
- unknown不补猜。
- adopted / locked 需用户确认范围。
- reroll不升级 Prompt version；改Prompt才升版。
- 上游改版使依赖下游标 STALE / NEEDS_REVIEW，不删除历史。
- Asset状态统一使用 planned / candidate / testing / adopted / locked / deprecated；不用 approved 与 adopted 双套同义状态。

## 6｜权限
总控：Project State、Task、跨模块block。
剧本：Script、Decision候选。
视觉资产：Asset、Asset Test；locked需用户。
导演：GEO、Shot Contract。
生成：Prompt、Generation。
QA：Issue、QA status、Repair route/retest。
剪辑：Edit。
用户：批准Decision、Selection、Lock和大框架。

## 7｜新窗口恢复
current focus object
→ current stage
→ active version
→ approved decisions
→ adopted / locked assets
→ open issues
→ last completed action
→ next action
→ do_not_change

## 8｜移动端默认展示
当前阶段｜当前对象｜当前采用版本｜当前问题｜当前动作｜下一步｜是否需要用户决定。
