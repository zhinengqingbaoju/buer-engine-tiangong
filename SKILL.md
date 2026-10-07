---
name: buer-engine-tiangong
description: 不二引擎·天工 AI影视生产系统。用于项目总控、剧本、视觉资产、GEO/分镜、图片与视频提示词编译、GPT/Seedance/MiniMax适配、生成前审计、生成记录、审片质检、返修、选片、剪辑后期与项目状态接续。执行前先读宪法和当前项目状态，再按岗位与阶段读取所需核心原文；不得以摘要替代四份原文。
---

# 不二引擎·天工

## Skill 自身的角色

本 Skill 只是**启动器 / 路由器 / 读取入口**。

它不拥有：
- 独立创作事实
- 独立项目状态
- 独立制作方法论
- 独立模型规则
- 覆盖宪法或四份核心原文的解释权

它只负责：
1. 先加载宪法与 PROJECT_STATE；
2. 判断当前阶段和目标岗位；
3. 按需加载对应 Role、核心原文、模板和 Adapter；
4. 检查入口条件；
5. 执行后把结果写回状态与记录。

如果 Skill 文本与宪法、当前项目事实、四份核心原文或当前官方/实测能力冲突，Skill 本身不得成为冲突中的“权威一方”，必须服从这些上位来源。

## 0｜最高规则

本 Skill **不是每个任务都必须加载的常驻前置步骤**。

只有以下情况才调用：
1. 用户从主要聊天/通用入口发起一个尚未明确归属哪个岗位的制作任务；
2. 任务跨越两个以上专业模块，需要系统判断路由、阶段或依赖；
3. 当前窗口需要查阅四份核心原文，但不确定应读哪份、哪一部分；
4. 当前任务需要从十一阶段、模型适配、QA返修等多个系统模块之间做仲裁；
5. 用户明确要求“按天工/HELL GRIND方法执行”。

已经处于明确专业窗口、任务归属清楚时，不必先调用 Skill。该窗口直接读取：
- 当前 `PROJECT_STATE` / 当前对象；
- 自己的 Role；
- 本任务真正需要的核心原文、模板或 Adapter。

纯状态查询、版本登记、文件归档、Drive链接回传、Task状态更新等操作，不需要为了形式加载 Skill 或四份核心原文。

没有当前项目状态时，不猜项目事实；由总控制片执行初始化或迁移盘点。

四份核心专业原文保持完整，不由本入口改写：
- [PROJECT_BRIEF.md](references/PROJECT_BRIEF.md)
- [LIRA SKILL.md](references/LIRA%20SKILL.md)
- [ACTING SKILL.md](references/ACTING%20SKILL.md)
- [CINEDANCE HIGGSFIELD SKILL.md](references/CINEDANCE%20HIGGSFIELD%20SKILL.md)

## 1｜运行顺序

如果任务从通用入口进入：
用户任务
→ 必要时调用 Skill 做路由
→ 确认目标岗位 / 阶段 / 对象
→ 目标岗位继续执行

如果任务已经在明确专业窗口：
用户任务
→ 读取当前 PROJECT_STATE / 当前对象
→ 读取本窗口 Role
→ 只加载本任务需要的核心正文 / 模板 / Adapter
→ 执行
→ 写真实 Record / 更新状态

不是所有任务都经过 Skill，也不是所有任务都读取四份核心。

不得把“写好Prompt”“准备提交”“生成成功”“QA通过”“用户采用”“锁定”混成一个状态。

## 2｜7个岗位

| 岗位 | Role |
|---|---|
| 主要聊天｜总控制片 | [ROLE_01_CONTROLLER.md](roles/ROLE_01_CONTROLLER.md) |
| 剧本叙事 | [ROLE_02_SCRIPT.md](roles/ROLE_02_SCRIPT.md) |
| 视觉资产 | [ROLE_03_VISUAL_ASSET.md](roles/ROLE_03_VISUAL_ASSET.md) |
| 导演分镜 | [ROLE_04_DIRECTOR.md](roles/ROLE_04_DIRECTOR.md) |
| 生成工程 | [ROLE_05_GENERATION.md](roles/ROLE_05_GENERATION.md) |
| 审片质检 | [ROLE_06_QA.md](roles/ROLE_06_QA.md) |
| 剪辑后期 | [ROLE_07_EDIT.md](roles/ROLE_07_EDIT.md) |

“资产锁定”不是独立岗位；它是资产状态。
“测试”不是独立岗位；它是生成工程的 TEST MODE。
“修理工”不是独立岗位；QA 开返修单并退回责任岗位，修后由 QA 复验。

## 3｜十一阶段

按 [PRODUCTION_PIPELINE.md](system/PRODUCTION_PIPELINE.md) 判断当前阶段和退出门。
阶段回答“什么时候做什么”；Role 回答“谁来做”；核心原文回答“专业上怎么做”；Adapter 回答“当前模型怎么提交”。

禁止把十一阶段机械等同于十一扇聊天窗口。

## 4｜按任务读取核心正文

### 项目/资产/空间/制作秩序
读取 PROJECT_BRIEF 对应正文。

### 图片资产、新建与局部编辑
读取 PROJECT_BRIEF 资产正文 + LIRA 对应任务正文 + 当前 Asset / Media Spec。

### 表演、行为、声音身份
读取 ACTING 对应正文；涉及镜头时同时读取当前 Shot / GEO。

### 分镜、摄影、视频Prompt
读取 CINEDANCE 对应正文 + 当前 Shot Contract + GEO + ACTING中本镜表演要求。

### 审片、失败诊断、返修
读取真实媒体 + Shot Contract / Asset / GEO + [QA_REPAIR_SYSTEM.md](system/QA_REPAIR_SYSTEM.md)；问题属于核心专业领域时再读对应原文。

### 剪辑与后期
读取 PROJECT_BRIEF 后期正文 + 当前 Selection / Edit Records。

搜索命中片段只用于定位；正式判断必须读取适用正文、条件、例外和模板上下文。

## 5｜模型编译

先读取 [PROMPT_COMPILER_CORE.md](system/PROMPT_COMPILER_CORE.md)。

静态图片：
[GPT_IMAGE_ADAPTER.md](adapters/GPT_IMAGE_ADAPTER.md)

Seedance 2.5：
[SEEDANCE_2_5_ADAPTER.md](adapters/SEEDANCE_2_5_ADAPTER.md)

MiniMax：
[MINIMAX_ADAPTER.md](adapters/MINIMAX_ADAPTER.md)

官方 API 能力、网页 UI 能力、Muse 实际入口能力分开记录。未验证项写 UNKNOWN / EXPERIMENTAL，不能补猜。

## 6｜共享状态与权限

数据模型：
[DATA_MODEL.md](system/DATA_MODEL.md)

状态与登记册：
[STATE_AND_REGISTRY.md](system/STATE_AND_REGISTRY.md)

每个窗口只写自己的授权字段。上游版本变化时，下游当前资格标 STALE / NEEDS_REVIEW，历史记录保留。

用户确认前：
- best / recommended 不能写 adopted
- adopted 不能自动写 locked
- Drive 已归档不能自动写压力测试通过

## 7｜Muse 当前运行方式

当前已实测：
- 共享 home workspace 可跨 Side Chat 读写
- Skill 可跨聊天触发
- Side Chat 只接受用户本人直接触发，不接受主聊天转发指令充当用户授权

因此当前协作：
主要聊天写 Task / next_action
→ 用户进入目标 Side Chat
→ 发送“执行待办”
→ 目标窗口读取共享状态与任务
→ 执行
→ 写回

未来 Muse 如果提供可信跨聊天任务机制，只升级 Runtime，不改变业务数据模型。

## 8｜交付与媒体

遵守 [STORAGE_DELIVERY_SPEC.md](system/STORAGE_DELIVERY_SPEC.md)。

图片生成结果包括候选、返修、未通过都必须保存 Google Drive；逐张给链接和状态；未经用户确认不得锁定。

Muse 当前原生音频内容理解测试失败。未有外部 STT / 可听模型 / 用户人工试听时，音频 QA 必须写 NOT_VERIFIED。

## 9｜来源与冲突

来源登记：[SOURCE_REGISTRY.md](provenance/SOURCE_REGISTRY.md)
字段来源：[FIELD_PROVENANCE_MATRIX.md](provenance/FIELD_PROVENANCE_MATRIX.md)
冲突仲裁：[SOURCE_ARBITRATION.md](provenance/SOURCE_ARBITRATION.md)

HELL GRIND 未取得附件必须标 MISSING；不二引擎重建内容必须明确标注，不冒充官方遗失原件。

遇到超出总指挥授权范围的冲突，呈现：
- 冲突双方
- 来源
- 实际影响
- 可选方案
交用户决定。
