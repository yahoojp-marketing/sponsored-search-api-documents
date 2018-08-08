# PageFeedItemReviewSummarySelector
The PageFeedItemReviewSummarySelector object stores search condition to acquire the examination results of the page feed item and the situation summary.

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field           | Data                          | response | getReviewSummary | Description            |
|-----------------|-------------------------------|----------|------------------|---------------|
| accountId       | xsd:long                      | -        | Requirement      | Account ID    |
| feedFolderIds[] | xsd:long                      | -        | Optional         | Feed folder ID |
| paging          | [Paging](../Common/Paging.md) | -        | Optional         | Setting of paging |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
