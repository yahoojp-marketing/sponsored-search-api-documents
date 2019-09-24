

# TargetingKeyword

TargetingKeyword contains keyword setting for Data Auto Insertion.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| targetingKeywordId | xsd:long | ID to identify the Targeting keyword (text).<br/>* To deactive, set &#34;0&#34;. | yes | - | - | Optional | - | |
| text | xsd:string | Keyword text.<br/>* Insert limit: Up to 80 characters and/or 10 words. | yes | - | Requirement | Requirement | - | |
| matchType | enum [KeywordMatchType](./KeywordMatchType.md) | Match type.<br/>To select what kind of matching to be made between the keywords and search query. | yes | - | Requirement | Requirement | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
