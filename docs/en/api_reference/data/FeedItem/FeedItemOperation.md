

# FeedItemOperation

FeedItemOperation contains the Feed Item information.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | - | - | Requirement | Requirement | Requirement | |
| placeholderType | enum [FeedItemPlaceholderType](./FeedItemPlaceholderType.md) | Type of Placeholder. | - | - | Requirement | Requirement | Requirement | |
| operand[1...2000] | [FeedItem](./FeedItem.md) | List of Feed Item.<br/>Each list includes the Feed Item details. | - | - | Requirement | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
