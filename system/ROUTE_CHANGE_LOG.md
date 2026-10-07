# ROUTE_CHANGE_LOG

## RC-ROUTE-001｜单一运行源修正
date: 2026-10-08
problem_found: 原INSTALL同时规划 /home/hatch/workspace/tiangong/ 和 ~/workspace/skills/buer-engine-tiangong/ 两套系统副本，存在双重权威与版本漂移风险。
old_route: GitHub RC → /workspace/tiangong → 再复制到Skill目录。
new_route: GitHub RC作为版本源；/home/hatch/workspace/skills/buer-engine-tiangong/ 作为Muse唯一运行副本；/home/hatch/workspace/projects/dongbei_xiyouji/ 只存项目状态。
reason: 单一事实源原则；减少未来更新、回滚与审计歧义。
evidence: PROJECT_STATE/单一事实源架构原则；Muse Skill可跨聊天调用的实测。
impact_scope: 安装路径与INSTALL说明。
framework_changed: no
rollback: 可恢复旧双目录结构，但不推荐。
result: INSTALL.md已更新。
approved_by: 总指挥Agent授权范围内的小范围实现修正。
