# 不二引擎·天工｜Muse冷启动候选包
版本：v01_RC_20261008
状态：PRE_DELIVERY_PASS / 非最终稳定版

## 这是什么
这是用于21.26 Muse冷启动安装的候选包。
“天工”是整个AI影视生产系统名称，不在Muse里额外注册一个运行Skill。
四份核心原文通过 runtime/system/CORE_BINDINGS.md 直接绑定7个专业岗位。

## 怎么用
1. 将整个ZIP上传到Muse主要聊天。
2. 把 00_给Muse执行_冷启动安装.md 作为安装任务执行。
3. 如Muse不能自动配置Side Chat，依次进入7个窗口，按 01_7窗口一次性初始化.md 初始化一次。
4. 完成后执行21.27四项快速验收。
5. 通过后再进入真实镜头验证。

## 当前项目事实
《东北西游记》锁定资产Source of Truth已经在交付前实时复核为：
东北西游记_锁定资产清单与归档规则_v15_20261008.md
共40张锁定原图；包内 project_seed/source/ 保存当前快照。
不要使用旧v09初始化。

## 包内不含运行Skill
本包故意不包含用于Muse注册的 SKILL.md / agents/openai.yaml。
GitHub仓库仍保留兼容入口，供未来天工正式版公开发布；Muse生产运行不依赖它。

## 当前已知限制
见 audit/KNOWN_LIMITATIONS.md。

## 预交付审查
见 audit/PRE_DELIVERY_6_LANE_AUDIT.md。
真正的最终六路Muse Agent终审仍在21.32执行。
