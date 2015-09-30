# CampaignCriterionSelector
Criteria for target campaign.
### Service
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd: long| Account ID. |
| campaignIds[]| xsd: long| Campaign ID. |
| criterionIds[]| xsd: long| Criterion. If you omit criterionIds field, return all of  criterionIds under the campaign ID. |
| criterionUse| enum <a href="../data/CriterionUse.md">CriterionUse</a>| Indicate the way a criterion is used.|
| paging| <a href="../data/Paging.md">Paging</a>| Holds the paging parameters such as starting index. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
