

# FeedItemSelector

FeedItemSelector describes the Feed item information.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Search condition: Account ID. | - | Requirement | - | - | - | |
| feedItemIds[0...1000] | xsd:long | Search condition: Feed Item ID. | - | Optional | - | - | - | |
| feedFolderIds[0...1000] | xsd:long | Search condition: Feed Folder ID. | - | Optional | - | - | - | |
| placeholderTypes[0...5] | enum [FeedItemPlaceholderType](./FeedItemPlaceholderType.md) | Search condition: Type of Feed Item. | - | Optional | - | - | - | |
| approvalStatuses[0...5] | enum [ApprovalStatus](./ApprovalStatus.md) | Search condition: Review status. | - | Optional | - | - | - | |
| paging | [Paging](../Common/Paging.md) | Search condition: Paging scope. | - | Optional | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
