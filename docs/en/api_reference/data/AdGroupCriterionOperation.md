# AdGroupCriterionOperation
AdGroupCriterionOperation displays target ad group criteria information and its operation results.
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| Operator. This field is required and should not be null.| Req |
| AdGroupCriterionOperation||||
| accountId| xsd:long| Account ID| Req |
| campaignId| xsd:long| Campaign ID| Req |
| adGroupId| xsd:long| Adgroup ID| Req |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| Select biddable or negative.| Req |
| operand| inherited <a href="./NegativeAdGroupCriterion.md">NegativeAdGroupCriterion</a><br><a href="./BiddableAdGroupCriterion.md">BiddableAdGroupCriterion</a>| The adgroup criterion being operated on. This field is required and should not be null.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
