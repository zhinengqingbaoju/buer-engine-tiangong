# CORE BINDINGS｜四核心资料自动岗位绑定
版本：v01_20261008

目的：四份核心资料不再通过“天工Skill”手动调用，而是按岗位/任务类型自动成为默认专业依据。完整原文仍保留在 references/，不拆坏、不改写。

## ROLE 01｜总控制片
默认不加载三专业Skill。
需要项目制作边界、资产/后期总原则时按需读取 PROJECT_BRIEF。
主要工作依据：宪法、11阶段、PROJECT_STATE、Task。

## ROLE 02｜剧本叙事
默认专业资料：
- ACTING：当任务涉及人物目标、行为逻辑、对白表演、反应、声音身份时自动读取适用正文。
PROJECT_BRIEF只在项目边界/制作事实需要时读取。
不默认加载 LIRA / CINEDANCE。

## ROLE 03｜视觉资产
默认专业资料：
- PROJECT_BRIEF：资产准备、身份一致性、空间/资产纪律的适用正文。
- LIRA：图片新建、局部编辑、身份、材质、构图、参考职责的适用正文。
不默认加载 ACTING / CINEDANCE，除非当前资产本身涉及表演母版或镜头用途。

## ROLE 04｜导演分镜
默认专业资料：
- CINEDANCE：镜头、摄影、空间、动作、物理、视频可执行性。
- ACTING：表演、调度、视线、反应、身体行为。
- PROJECT_BRIEF：GEO、连续性、资产/空间约束的适用正文。
不默认加载 LIRA，除非镜头发现必须补/改图片资产。

这是“导演岗位”的默认专业底座，不需要用户额外说“调用导演Skill”。

## ROLE 05｜生成工程
按 task_type 自动绑定：
- image_new / image_edit / image_rebuild：
  LIRA + GPT_IMAGE_ADAPTER + 当前Asset/MediaSpec。
- video：
  CINEDANCE + 当前Shot/GEO；涉及人物表演时追加 ACTING；再加载 Seedance/MiniMax Adapter。
- simple record / upload / status：
  不加载四核心，只按Generation/Storage规则执行。
生成工程不得因此改写上游事实。

## ROLE 06｜审片质检
按问题类别自动读取：
- identity / image / material / edit defect → LIRA + PROJECT_BRIEF相关正文
- acting / gaze / reaction / voice-performance → ACTING
- camera / blocking / action / physics / video prompt execution → CINEDANCE
- continuity / asset / production / post → PROJECT_BRIEF
如果问题类别清楚，只读必要资料，不整包加载。

## ROLE 07｜剪辑后期
默认专业资料：
- PROJECT_BRIEF 后期、清理、调色、声音相关正文。
只有发现镜头/表演/生成源问题需要回上游时，才读取相应Skill。

## 共同原则
1. 自动绑定 ≠ 每次整份全文塞进上下文；只读取当前任务需要的原文段落及必要上下文。
2. 四核心是专业依据；Role负责岗位权限；11阶段负责时序；Adapter负责模型提交。
3. 同一规则不在Role里重写一套，只引用来源。
4. 用户无需手动“启动天工Skill”或“调用导演Skill”。
5. 纯机械状态/归档/链接/版本操作不加载任何核心Skill。
