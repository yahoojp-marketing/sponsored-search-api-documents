

# MultipleFeedItemAttribute

MultipleFeedItemAttribute object holds the value of FeedItem attribution information.
This object is applied when the following placeholderFields are used.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

### Inheritance

+ [FeedItemAttribute](./FeedItemAttribute.md)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| feedAttributeValues[] | [FeedAttributeValue](./FeedAttributeValue.md) | Value of FeedItem information.<br/>*ADDITIONAL_ADVANCED_URLS, ADDITIONAL_ADVANCED_MOBILE_URLS and STRUCTURED_SNIPPET_VALUES can be set up to 9 items. | yes | - | Requirement | Requirement<br/> | - | |
| isRemove | enum [IsRemove](./IsRemove.md) | Remove FeedItem.<br/>*To remove MultipleFeedAttributeValue, need to specify &#34;isRemove=TRUE&#34;. | - | - | - | Optional | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
