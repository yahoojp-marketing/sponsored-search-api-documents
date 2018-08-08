# PageFeedItemSelector

PageFeedItemSelector object stores search condition to inquire about registered page feed item.

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field               | Type                                                               | response | get         | Discription                |
|---------------------|--------------------------------------------------------------------|----------|-------------|-------------------|
| accountId           | xsd:long                                                           | -        | Requirement | Account ID        |
| feedFolderIds[]     | xsd:long                                                           | -        | Requirement | Feed folder ID     |
| approvalStatuses[]  | enum [PageFeedItemApprovalStatus](./PageFeedItemApprovalStatus.md) | -        | Optional    | Kind of approval stratus |
| pageFeedUrl[]       | [PageFeedUrl](./PageFeedUrl.md)                                    | -        | Optional    | Search condition of page feed URL|
| pageFeedCustomLabel | xsd:string                                                         | -        | Optional    | Custom label|
| paging              | [Paging](../Common/Paging.md)                                      | -        | Optional    | Setting of paging |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
