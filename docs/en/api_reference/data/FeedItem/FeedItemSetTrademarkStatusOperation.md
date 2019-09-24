

# FeedItemSetTrademarkStatusOperation

FeedItemSetTrademarkStatusOperation object holds the target's trademark restriction information.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | setTrademarkStatus |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Account ID | - | Requirement | |
| placeholderType | enum [FeedItemPlaceholderType](./FeedItemPlaceholderType.md) | Type of feed item | - | Requirement | |
| operand[0...2000] | [FeedItemSetTrademarkStatus](./FeedItemSetTrademarkStatus.md) | Array of trademark restriction | - | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
