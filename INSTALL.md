# Muse 冷启动安装说明（RC）

目标分支：rebuild-v01-rc-20261007
基础核心原文来自本仓库 references/，不改动。

## 单一运行源

正式运行时只保留一份天工本体：

/home/hatch/workspace/skills/buer-engine-tiangong/

不得再复制一份到 /home/hatch/workspace/tiangong/，避免系统文件出现双重权威。

项目状态单独存放：

/home/hatch/workspace/projects/dongbei_xiyouji/

GitHub RC 分支负责版本源；Muse Skill 目录负责运行；项目目录负责项目状态。三者职责分离。

安装顺序：
1. 只在用户明确执行21.26时清理旧聊天、测试Skill、tiangong_smoke_test；保留必要即梦/MiniMax登录状态与连接授权。
2. 将本候选分支内容部署到 /home/hatch/workspace/skills/buer-engine-tiangong/，作为唯一运行副本。
3. 校验 SKILL.md、system/、roles/、adapters/、templates/、provenance/、references/、project_init/ 均存在；四份核心 references SHA 必须与登记值一致。
4. 创建 /home/hatch/workspace/projects/dongbei_xiyouji/ 及 PROJECT_STATE、TASK_QUEUE、Registries、records 目录。
5. 导入 project_init/DBXYJ_INIT.md 的当前有效事实；锁定资产以 v09 Drive 清单为 Source of Truth。
6. 建7窗口：主要聊天、剧本叙事、视觉资产、导演分镜、生成工程、审片质检、剪辑后期。
7. 当前调度：总控写Task→用户在目标Side Chat发送“执行待办”→窗口读共享状态→执行→回写。不要让主聊天转发命令冒充用户指令。
8. 跑四项快速验收：Skill跨窗、State跨窗读写、越权拒绝、执行待办链。

通过四项后进入真实项目验证；未通过则记录 BLOCKED，不回退成旧9窗口。
