# NegativeCampaignCriterion
NegativeCampaignCriterion object describes the negative criteria in campaign level.

### Service
+ [CampaignCriterionService](../../services/CampaignCriterionService.md)

### Namespace
[CampaignCriterionService#Namespace](../../services/CampaignCriterionService.md#namespace)

| Field | Data Type | Description | ADD | REMOVE | 
|---|---|---|---|---|
| CampaignCriterion(inherited)|||||
| accountId| xsd:long| Account ID. | Req| Req |
| campaignId| xsd:long| Campaign ID. | Req| Req |
| campaignName| xsd:string| Campaign Name. | ─| ─ |
| criterionUse| enum <a href="CampaignCriterionUse.md">CampaignCriterionUse</a>| Select the criterion's ability, individual bid available or excluded.| Req| Req |
| criterion| <a href="Criterion.md">Criterion</a><br>inherited <a href="Keyword.md">Keyword</a>| The criterion part of the campaign criterion. | Req| Req |
| NegativeCampaignCriterion|||||

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
