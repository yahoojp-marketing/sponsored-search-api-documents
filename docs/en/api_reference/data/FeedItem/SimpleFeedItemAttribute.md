

# SimpleFeedItemAttribute

SimpleFeedItemAttribute object stores the value of attribution information of feed items.
This object is applied for the following placeholderFields.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

### Inheritance

+ [FeedItemAttribute](./FeedItemAttribute.md)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| feedAttributeValue | xsd:string | Value of feed iteim information.<br/><br/>*When using data insertion, you need to enter attribution as follows:<br/>・AD_CUSTOMIZER_INTEGER<br/>ex) 99999999<br/>・AD_CUSTOMIZER_PRICE<br/>ex) 19800 or 19,800<br/>・AD_CUSTOMIZER_DATE<br/>ex) 20151231 235959<br/>・AD_CUSTOMIZER_STRING<br/>ex) home<br/>・STRUCTURED_SNIPPET_HEADER<br/>ex) brand<br/> | yes | - | Requirement | Optional | Ignore | |
| reviewFeedAttributeValue | xsd:string | The feed item information on editorial review.<br/>*It is displayed for response only on Editorial Review. | yes | - | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
