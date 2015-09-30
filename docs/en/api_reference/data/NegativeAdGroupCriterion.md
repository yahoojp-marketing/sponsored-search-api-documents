# NegativeAdGroupCriterion
NegativeAdGroupCriterion object displays negative criteria in ad group.
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| AdGroupCriterion(inherited)|||||
| accountId| xsd:long| Account ID.| Req| ReqNotUpdatable |
| campaignId| xsd:long| Campaign ID.| Req| ReqNotUpdatable |
| campaignName| xsd:string| Campaign name.| Ignore| IgnoreNotUpdatable |
| adGroupId| xsd:long| The ad group this criterion is in. This field is required and should not be null.| Req| ReqNotUpdatable |
| adGroupName| xsd:string| AdGroup name.| Ignore| IgnoreNotUpdatable |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| Biddable or negative.| Req| IgnoreNotUpdatable |
| criterion| <a href="./Criterion.md">Criterion</a><br>inherited <a href="./Keyword.md">Keyword</a>| The criterion part of the ad group criterion. This field is required and should not be null.| Req| ReqNotUpdatable |
| NegativeAdGroupCriterion|||||
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
