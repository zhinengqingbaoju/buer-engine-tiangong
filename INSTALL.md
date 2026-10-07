# Muse 冷启动安装说明（RC）
版本：v01_20261008

目标分支：rebuild-v01-rc-20261007
四份核心原文来自本仓库 references/，保持原文不改。

## 单一运行源

Muse 正式运行只保留一份天工系统本体：

/home/hatch/workspace/tiangong/

项目状态单独存放：

/home/hatch/workspace/projects/dongbei_xiyouji/

GitHub RC = 版本/开发来源；
/home/hatch/workspace/tiangong/ = Muse 唯一系统运行目录；
projects/dongbei_xiyouji/ = 项目数据。

Muse 冷启动包不把 `SKILL.md` 或 `agents/openai.yaml` 注册成运行 Skill。
“天工”是系统名称；四核心通过 `system/CORE_BINDINGS.md` 直接绑定7个岗位。

## 安装顺序

1. 删除/停用旧版天工 Skill、旧测试 Skill、旧9窗口测试聊天与 tiangong_smoke_test；保留必要的即梦/MiniMax登录状态和连接授权。
2. 将新版系统包完整放入 /home/hatch/workspace/tiangong/。
3. 校验 system/、roles/、adapters/、templates/、provenance/、references/、project_init/ 均存在。
4. 校验四核心 references SHA 与 SOURCE_REGISTRY 一致。
5. 创建 /home/hatch/workspace/projects/dongbei_xiyouji/，初始化 PROJECT_STATE、TASK_QUEUE、Registries、records。
6. 导入 project_init/DBXYJ_INIT.md；锁定资产以 v15 Drive 清单为项目 Source of Truth。
7. 建立7个窗口：主要聊天、剧本叙事、视觉资产、导演分镜、生成工程、审片质检、剪辑后期。
8. 每个窗口一次性写入其岗位启动指令；之后直接按岗位工作，不要求用户调用“天工 Skill”。
9. 当前跨窗调度：总控写 Task → 用户进入目标 Side Chat 发送“执行待办” → 窗口读共享状态/任务 → 执行 → 回写。
10. 跑4项快速验收。

## 21.27 四项快速验收

A｜PROJECT_STATE 跨窗口读写：
窗口A写测试状态，窗口B能读到同一值。

B｜岗位越权拒绝：
例如视觉资产窗口收到“修改已锁中文对白”，应拒绝并路由剧本/用户。

C｜四核心自动岗位绑定：
导演分镜窗口接到导演任务时，应自动使用 CINEDANCE + ACTING + PROJECT_BRIEF相关正文；视觉资产自动使用 Brief + LIRA。不得要求用户手动启动 Skill。

D｜“执行待办”任务链：
主要聊天写 Task；目标窗口收到用户“执行待办”后能读取、执行并正确回写。

四项通过后进入真实项目验证。未通过记录 BLOCKED，不回退成旧9窗口。
