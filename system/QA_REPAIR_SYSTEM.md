# 质检—返修—回归系统
版本：v01_20261007

QA顺序：读当前合同/资产→实际看完整媒体→Expected vs Observed→证据位置→严重度→责任层→根因状态→route→返修后目标+回归复验。

严重度：S1阻断核心身份/剧情/对白/动作/连续性；S2明显影响可用性；S3次要可后期/酌情；S4审美差异/优化。

Route：REROLL（随机失败）/ REWRITE（重复稳定偏差）/ ASSET / GEOGRAPHY / REDESIGN（结构过载）/ POST。

返修必填：issue_id,changed_variables,preserve_requirements,source_version,new_version,expected_improvement,retest_result,regression_result。

停止线：连续返修不收敛→重判责任层；多并发动作冲突→拆镜；身份持续漂移→回资产；平台不支持→unsupported/换模式，不伪造成功。

Muse当前原生音频内容理解FAIL；未接STT/可听模型/人工试听时 audio_qa_status=NOT_VERIFIED，不能宣称完整声画QA PASS。
QA PASS不等于adopted；用户确认后才adopted/locked。
