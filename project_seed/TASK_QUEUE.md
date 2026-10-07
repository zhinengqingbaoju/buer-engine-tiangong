# TASK_QUEUE

## MIG-001
target_object: DBXYJ_CURRENT_PROJECT_STATE
stage: MIGRATION
target_role: CONTROLLER
goal: 读取当前有效项目文件、v15锁定资产清单、有效剧本/分镜/未完成事项，把当前真实生产焦点迁入新版PROJECT_STATE与各Registries；不得把历史候选升级为当前事实。
required_inputs:
  - project_init/DBXYJ_INIT.md
  - 东北西游记_锁定资产清单与归档规则_v15_20261008
  - 当前有效剧本/分镜/提示词/生成记录
preserve_requirements:
  - 用户已确认创作事实
  - 锁定资产状态
  - 狐仙堂覆盖旧天宫地点表述
permissions:
  - 可登记/迁移当前事实
  - 不可改变创作内容
status: ready
result_refs:
