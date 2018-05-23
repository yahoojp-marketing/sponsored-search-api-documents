# CampaignCriterionOperation
CampaignCriterionOperationオブジェクトは、操作の対象となるキャンペーンのクライテリアと処理の内容を表します。
### Service
+ [CampaignCriterionService](../../services/CampaignCriterionService.md)

### Namespace
[CampaignCriterionService#Namespace](../../services/CampaignCriterionService.md#namespace)

| フィールド | データ型 | 説明 | 制限 |
|---|---|---|---|
| Operation(inherited)||||
| operator| enum Operator|ADD、SET、REMOVEが指定可能です。 | Req |
| CampaignCriterionOperation||||
| accountId| xsd:long| アカウントIDです。| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req |
| criterionUse| enum <a href="CampaignCriterionUse.md">CampaignCriterionUse</a>| クライテリアを単価設定可能にするか除外にするかを選択します。| Req |
| operand[]| <a href="CampaignCriterion.md">CampaignCriterion</a><br>inherited <a href="NegativeCampaignCriterion.md">NegativeCampaignCriterion</a>| 処理の対象となるキャンペーンのクライテリア情報が含まれます。| Req |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
