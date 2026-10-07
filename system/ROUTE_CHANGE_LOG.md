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


## RC-ROUTE-002｜Skill从“每任务加载”改为“条件触发”
date: 2026-10-08
problem_found: 原入口设计容易让所有专业窗口每个任务都先加载Skill，造成重复路由、上下文浪费，并在纯状态/归档任务中引入无关制作规则。
old_route: 每个任务自动先走Skill。
new_route: Skill仅用于通用入口路由、跨模块任务、阶段/依赖判断、核心资料导航或用户明确点名天工；专业窗口任务归属明确时直接读取Role + 当前State + 必要资料。
reason: Skill的本质是路由器，不是常驻中间件。
impact_scope: SKILL.md、主要聊天调用逻辑。
framework_changed: no
rollback: 可恢复，但不推荐。
result: 已修订。
approved_by: 用户明确指出“有的流程Skill没用”，总指挥按小范围实现授权修正。


## RC-ROUTE-003｜消除 Skill 与 11 阶段/状态/交付规则重叠
date: 2026-10-08
problem_found: Skill 仍重复描述生产运行顺序、状态规则、Muse运行和交付纪律，与 PRODUCTION_PIPELINE / STATE_AND_REGISTRY / STORAGE_DELIVERY_SPEC 等模块形成重叠。
old_route: Skill兼具路由入口和部分流程/状态规则复述。
new_route: Skill压缩为纯条件路由器，只回答“去哪个岗位、读哪些资料、依赖顺序是什么”；十一阶段、权限、状态、交付和模型规则全部由各自唯一模块负责。
reason: 避免双重权威、重复上下文和后续版本漂移。
impact_scope: SKILL.md。
framework_changed: no
rollback: 可恢复，但不推荐。
result: 已修订。
approved_by: 总指挥Agent在既有小范围授权内执行。


## RC-ROUTE-004｜天工从运行Skill改为系统总名，四核心直接绑定岗位
date: 2026-10-08
problem_found: 继续保留“天工运行Skill”会在11阶段、7岗位和四核心之外形成多余调用层；用户指出原天工本质是 PROJECT_BRIEF 总则 + LIRA / ACTING / CINEDANCE 三个专业Skill。
old_route: 任务在需要时先进入天工Skill路由，再到岗位。
new_route: 天工仅作为整个生产系统名称；SKILL.md只保留安装/系统清单用途。四核心按岗位和task_type自动绑定：视觉资产→Brief+LIRA；导演分镜→CINEDANCE+ACTING+Brief；生成工程按图片/视频任务自动加载；QA按问题类型加载；剪辑→Brief后期。用户不再手动启动天工或专业Skill。
reason: 消除额外中间层和规则互斥，使专业知识直接落在责任岗位。
impact_scope: SKILL.md、CORE_BINDINGS.md、Role默认资料绑定。
framework_changed: no；仍保持11阶段+7岗位+四核心+状态/模板/Adapter。
rollback: 可恢复运行Skill，但不推荐。
result: 已实施。
approved_by: 用户明确提出该结构。
