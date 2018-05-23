# CampaignCriterionSelector
CampaignCriterionSelector object describes campaign criteria for operation.
### Service
+ [CampaignCriterionService](../../services/CampaignCriterionService.md)

### Namespace
[CampaignCriterionService#Namespace](../../services/CampaignCriterionService.md#namespace)

| Field | Type | Description | 
|---|---|---|
| accountId| xsd: long| Account ID. |
| campaignIds[0..500]| xsd:long| Campaign ID array. |
| criterionIds[0..500]| xsd:long| Criterion ID array. <br>If no criterionIds, all of criterionIds under the campaign ID are returned. |
| criterionUse| enum <a href="CampaignCriterionUse.md">CampaignCriterionUse</a>| Select the criterion's ability, individual bid available or excluded.|
| paging| <a href="../Common/Paging.md">Paging</a>| Holds the paging scope. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
