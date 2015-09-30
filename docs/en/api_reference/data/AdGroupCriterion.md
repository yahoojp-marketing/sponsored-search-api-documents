# AdGroupCriterion
AdGroupCriterion object describes ad group criteria information.
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID |
| campaignId| xsd:long| Campaign ID |
| campaignName| xsd:string| Campaign name |
| adGroupId| xsd:long| The ad group this criterion is in. This field is required and should not be null. |
| adGroupName| xsd:string| AdGroup name |
| criterionUse| enum <a href="../data/CriterionUse.md">CriterionUse</a>| Select biddable or negative. |
| criterion| <a href="../data/Criterion.md">Criterion</a><br>inherited <a href="../data/Keyword.md">Keyword</a>| The criterion part of the ad group criterion. This field is required and should not be null. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
