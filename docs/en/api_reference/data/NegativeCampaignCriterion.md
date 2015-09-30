# NegativeCampaignCriterion
Negative criteria in campaign level.
### Service
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

| Field | Data Type | Description | 
|---|---|---|
| CampaignCriterion(inherited)|||
| accountId| xsd:long| Account ID. |
| campaignId| xsd:long| Campaign ID. |
| campaignName| xsd:string| Campaign Name. |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| Biddable or negative.|
| criterion| <a href="./Criterion.md">Criterion</a><br>inherited <a href="./Keyword.md">Keyword</a>| The criterion part of the campaign criterion. |
| NegativeCampaignCriterion|||
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
