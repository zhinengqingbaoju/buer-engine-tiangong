---
name: buer-engine-tiangong
description: 不二引擎·天工的按需导航入口。仅在任务归属不明确、跨模块、需要判断阶段/依赖、需要定位四份核心原文，或用户明确要求按天工/HELL GRIND执行时调用。它不拥有独立制作规则、项目事实或创作权。
---

# 不二引擎·天工｜导航入口

## 1｜Skill 的唯一角色

本 Skill 只负责：
1. 判断当前任务是否需要天工导航；
2. 读取当前 PROJECT_STATE / 当前对象；
3. 判断应由哪个专业岗位处理；
4. 指向需要读取的核心原文、系统文件、模板或模型 Adapter；
5. 如果任务跨模块，指出依赖顺序和应返回的责任层。

本 Skill 不负责：
- 定义十一阶段流程；
- 定义岗位权限；
- 定义资产/镜头/Prompt/QA/交付规则；
- 保存项目事实；
- 改写四份核心原文；
- 代替目标岗位执行专业工作。

若本 Skill 与宪法、当前项目事实、四份核心原文、正式系统模块或当前官方/实测能力冲突，本 Skill 无权覆盖它们。

## 2｜什么时候调用

仅在以下情况调用：
- 从主要聊天/通用入口收到尚未明确归属的制作任务；
- 任务跨两个以上专业模块，需要判断先后依赖；
- 需要判断当前处于十一阶段哪一步；
- 当前窗口需要四份核心原文，但不知道应读哪份/哪一段；
- 需要在 Prompt、模型适配、QA返修等模块之间做路由；
- 用户明确要求“按天工”或“按 HELL GRIND 方法”执行。

以下情况默认不调用：
- 已在明确专业窗口且任务归属清楚；
- 纯 PROJECT_STATE 查询；
- Task 状态更新；
- 版本登记；
- 文件归档；
- Google Drive 链接回传；
- 已明确模板的简单填充；
- 其他不需要跨模块判断的机械操作。

## 3｜导航入口

### 制作阶段
需要判断“现在做到哪一步、退出门、返工去哪”：
→ [PRODUCTION_PIPELINE.md](system/PRODUCTION_PIPELINE.md)

### 7个专业岗位
总控制片 → [ROLE_01_CONTROLLER.md](roles/ROLE_01_CONTROLLER.md)
剧本叙事 → [ROLE_02_SCRIPT.md](roles/ROLE_02_SCRIPT.md)
视觉资产 → [ROLE_03_VISUAL_ASSET.md](roles/ROLE_03_VISUAL_ASSET.md)
导演分镜 → [ROLE_04_DIRECTOR.md](roles/ROLE_04_DIRECTOR.md)
生成工程 → [ROLE_05_GENERATION.md](roles/ROLE_05_GENERATION.md)
审片质检 → [ROLE_06_QA.md](roles/ROLE_06_QA.md)
剪辑后期 → [ROLE_07_EDIT.md](roles/ROLE_07_EDIT.md)

### 四份核心专业原文
资产准备、空间、制作纪律、返修、后期：
→ [PROJECT_BRIEF.md](references/PROJECT_BRIEF.md)

图片资产、新建与局部编辑：
→ [LIRA SKILL.md](references/LIRA%20SKILL.md)

人物表演、行为、声音：
→ [ACTING SKILL.md](references/ACTING%20SKILL.md)

视频提示词、摄影、动作、物理、声音：
→ [CINEDANCE HIGGSFIELD SKILL.md](references/CINEDANCE%20HIGGSFIELD%20SKILL.md)

跨领域任务按需读取多份正文。搜索命中只用于定位，正式判断必须读取适用条件、上下文和例外。

### 系统模块
数据对象：
→ [DATA_MODEL.md](system/DATA_MODEL.md)

项目状态/登记册：
→ [STATE_AND_REGISTRY.md](system/STATE_AND_REGISTRY.md)

Prompt 编译核心：
→ [PROMPT_COMPILER_CORE.md](system/PROMPT_COMPILER_CORE.md)

QA/返修：
→ [QA_REPAIR_SYSTEM.md](system/QA_REPAIR_SYSTEM.md)

文件/版本/Google Drive交付：
→ [STORAGE_DELIVERY_SPEC.md](system/STORAGE_DELIVERY_SPEC.md)

### 模型适配器
GPT 图片：
→ [GPT_IMAGE_ADAPTER.md](adapters/GPT_IMAGE_ADAPTER.md)

Seedance 2.5：
→ [SEEDANCE_2_5_ADAPTER.md](adapters/SEEDANCE_2_5_ADAPTER.md)

MiniMax：
→ [MINIMAX_ADAPTER.md](adapters/MINIMAX_ADAPTER.md)

## 4｜导航输出格式

Skill 只需给目标岗位/系统返回：

- current_object
- current_stage（需要时）
- target_role
- required_sources
- required_templates
- required_adapter（需要时）
- dependency_order（跨模块时）
- blocking_issue（如有）

然后退出导航，由目标岗位继续执行。

## 5｜来源真实性

来源登记：
→ [SOURCE_REGISTRY.md](provenance/SOURCE_REGISTRY.md)

字段来源：
→ [FIELD_PROVENANCE_MATRIX.md](provenance/FIELD_PROVENANCE_MATRIX.md)

冲突仲裁：
→ [SOURCE_ARBITRATION.md](provenance/SOURCE_ARBITRATION.md)

HELL GRIND 未取得附件必须保持 MISSING；不二引擎重建内容不得冒充官方遗失原件。
