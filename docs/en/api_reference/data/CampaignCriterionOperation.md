# CampaignCriterionOperation
CampaignCriterionOperation object describes campaign criteria for operation and list of operations.
### Service
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| Operator.| Req |
| CampaignCriterionOperation||||
| accountId| xsd:long| Account ID.| Req |
| campaignId| xsd:long| Campaign ID.| Req |
| criterionUse| enum <a href="./CampaignCriterionUse.md">CampaignCriterionUse</a>| Select the criterion's ability, individual bid available or excluded.| Req |
| operand[]| <a href="./CampaignCriterion.md">CampaignCriterion</a><br>inherited <a href="./NegativeCampaignCriterion.md">NegativeCampaignCriterion</a>| The campaign criteria information for operation is included. | Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
