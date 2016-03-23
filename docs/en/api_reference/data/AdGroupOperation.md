# AdGroupOperation
AdGroupOperation displays target ad group information and its operation results.
### Service
+ [AdGroupService](../services/AdGroupService.md)

| Field | Data Type | Description | Restrictions |
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| Operator. This field is required and should not be null.| Req |
| AdGroupOperation||||
| accountId| xsd:long| account ID.| Req |
| operand[]| <a href="./AdGroup.md">AdGroup</a>| AdGroup to operate on This field is required and should not be null.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
