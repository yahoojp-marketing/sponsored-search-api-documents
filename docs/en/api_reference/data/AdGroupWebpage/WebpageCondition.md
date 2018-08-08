# WebpageCondition
WebpageCondition object contains the rules of webpage.

### Service
+ [AdGroupWebpageService](../../services/AdGroupWebpageService.md)

### Namespace
[AdGroupWebpageService#Namespace](../../services/AdGroupWebpageService.md#namespace)

| Field | Type | Description | response | add | set | remove
|---|---|---|---|---|---|---|
|type| enum [WebpageConditionType](./WebpageConditionType.md) | Rule type of Web page<br>&lowast;Only one ALL_PAGES can be set in ad group. Can not be set when excluding. | yes | Req | Ignore | Ignore |
|argument| xsd:string | Value of rule setting (Can specify regular expression) | yes | Req<br>&lowast;If type is ALL_PAGES, Optional | Ignore | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
