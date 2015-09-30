# Keyword
Keyword object displays keyword information.
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Criterion(inherited)||||||
| criterionId| xsd:long| ID of this criterion.| Ignore| ReqNotUpdatable| ReqNotUpdatable |
| type| enum <a href="./CriterionType.md">CriterionType</a>| This field indicates the subtype of Criterion of this instance.| Req| ReqNotUpdatable| ReqNotUpdatable |
| Keyword||||||
| text| xsd:string| Text of this keyword (Maximum of 80 characters and ten words).| Req| Ignore| Ignore |
| matchType| enum <a href="./KeywordMatchType.md">KeywordMatchType</a>| Match type of this keyword. This field is required and should not be null.| Req| Ignore| Ignore |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
