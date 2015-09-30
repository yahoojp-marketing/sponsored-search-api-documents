# CampaignCriterionOperation
Campaign criteria and its operation.
### Service
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| Operator. This field is required and should not be null.| Req |
| CampaignCriterionOperation||||
| accountId| xsd:long| Account ID| Req |
| campaignId| xsd:long| Campaign ID| Req |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| Indicate the way a criterion is used| Req |
| operand[]| <a href="./CampaignCriterion.md">CampaignCriterion</a><br>inherited <a href="./NegativeCampaignCriterion.md">NegativeCampaignCriterion</a>| The campaign criterion being operated on. This field is required and should not be null.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
