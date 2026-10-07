# 《东北西游记》项目初始化
版本：v01_20261007

project_id: DBXYJ_2026
project_name: 东北西游记
creator: 姜德雨
system: 不二引擎·天工
类型：现代东北农村 × 西游神话人物 × 强情境喜剧
视觉：东方神话现实主义为主、荒诞现实电影为辅；真实电影级、非卡通
语言：当代真实东北口语，不用“俺”等刻板标签
人物：西游人物保留人格、能力与尊严；喜剧来自欲望、关系、现实冲突
current_stage: UNKNOWN_PENDING_MIGRATION_AUDIT

当前硬决定：
- 用户掌握故事、对白、主要外观、风格、关键镜头和最终采用。
- 提示词：英文视觉/动作/摄影 + 逐字中文对白；固定资产描述逐字复用。
- 10秒麻将字牌片头地点=狐仙堂，不是天宫；旧“天宫麻将桌/偏殿”地点表述失效。
- 历史目录“狐仙庙”可保留文件名，但生产事实用“狐仙堂”。

锁定资产Source of Truth：
东北西游记_锁定资产清单与归档规则_v15_20261007.md
https://drive.google.com/file/d/1b2PYRiBPja1HGWMHiwKsmDSYqhbpF7_j/view?usp=drivesdk
统一入口：https://drive.google.com/drive/folders/1ydeEH8s3WeKNjF0kiwEJKZxIIyRQKnzD
v15记录40张锁定原图。导入时不得把候选/历史参考升级为锁定。

关键当前资产链接由v15清单解析到ASSET_REGISTRY，不在本初始化文件重复定义人物描述，避免双重事实源。

迁移警告：现有“10秒宣传片剧本v04”仍含“天宫偏殿”，导入历史但标 SCRIPT_NEEDS_PATCH_LOCATION；安装后由剧本窗口生成新版本，将地点更新为狐仙堂，不静默覆盖v04，其他已确认动作/时间/人物/道具保持。

已知限制：多个人物十次压力测试未完成；若真实镜头需要则补测，不把locked写成stress-tested。Seedance视频模式参考上传/参数待实战验证。Muse音频自动QA不可用。
