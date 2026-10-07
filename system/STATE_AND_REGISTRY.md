# PROJECT_STATE 与登记册
版本：v01_20261007

存储分层：
1 PROJECT_STATE：当前指针/摘要，保持短。
2 Registries：当前正式事实。
3 Records：历史事件/产物。
4 Media：真实媒体在Google Drive/平台，状态只保存引用。

PROJECT_STATE：project_id,project_name,current_stage,current_episode,current_scene,current_shot,active_script_version,active_visual_direction_version,active_pipeline_version,active_role_schema_version,active_adapter_versions,active_asset_set,open_issue_count,unresolved_decisions,blocked_items,last_completed_action,next_action,next_role,updated_at

Registries：DECISION_REGISTRY / ASSET_REGISTRY / SCENE_REGISTRY / SHOT_REGISTRY / TASK_QUEUE
Records：PROMPT / GENERATION / ISSUE / REPAIR / SELECTION / EDIT / ROUTE_CHANGE

原则：聊天不是事实源；active显式；历史保留；unknown不补猜；locked/adopted需用户；reroll不升Prompt版本；改词才升；上游改版→下游STALE/NEEDS_REVIEW。

权限：总控写项目级State/Task；剧本写Script/Decision候选；视觉资产写Asset；导演写GEO/Shot；生成写Prompt/Generation；QA写Issue/QA/Repair route；剪辑写Edit；用户批准Decision/Selection/Lock/大框架。

新窗口恢复顺序：stage→current object→active version→approved decisions→adopted/locked assets→open issues→last action→next action→do_not_change。
移动端默认只展示：当前阶段｜对象｜采用版本｜问题｜正在做什么｜下一步｜是否需用户决定。
