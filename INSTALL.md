# Muse 冷启动安装说明（RC）

目标分支：rebuild-v01-rc-20261007
基础核心原文来自本仓库 references/，不改动。

目标路径：
/home/hatch/workspace/tiangong/
~/workspace/skills/buer-engine-tiangong/
/home/hatch/workspace/projects/dongbei_xiyouji/

安装顺序：
1. 只在用户明确执行21.26时清理旧聊天/测试Skill/tiangong_smoke_test；保留必要即梦/MiniMax登录状态与连接授权。
2. 获取本候选分支文件到 /home/hatch/workspace/tiangong/。
3. 将SKILL.md及其引用目录安装/复制到Muse可发现的skills路径；保持单一Skill来源。
4. 创建projects/dongbei_xiyouji/及PROJECT_STATE、TASK_QUEUE、Registries、records目录。
5. 导入 project_init/DBXYJ_INIT.md 的当前有效事实；锁定资产以v09 Drive清单为Source of Truth。
6. 建7窗口：主要聊天、剧本叙事、视觉资产、导演分镜、生成工程、审片质检、剪辑后期。
7. 当前调度：总控写Task→用户在目标Side Chat发送“执行待办”→窗口读共享状态→执行→回写。不要让主聊天转发命令冒充用户指令。
8. 跑四项快速验收：Skill跨窗、State跨窗读写、越权拒绝、执行待办链。

通过四项后进入真实项目验证；未通过则记录BLOCKED，不回退成旧9窗口。
