# AdGroupAdOperation
Ad and operations to call.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| Operator.| Req |
| AdGroupAdOperation||||
| accountId| xsd:long| Account ID| Req |
| campaignId| xsd:long| Campaign ID| Req |
| adGroupId| xsd:long| AdGroup ID| Req |
| operand[]| <a href="./AdGroupAd.md">AdGroupAd</a>| AdGroupAd to operate on.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
