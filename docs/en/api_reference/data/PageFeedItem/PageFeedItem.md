# PageFeedItem
PageFeedItem object retains page feed Item.

## Service
- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace
[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field | Type | response | Description |
|--------------------------|--------------------------------------------------------------------|----------|----------------------------------------|
| accountId                | xsd:long                                                           | yes      | Account ID |
| feedFolderId             | xsd:long                                                           | yes      | Feed folder ID |
| pageFeedItemId           | xsd:long                                                           | yes      | Page feed item ID |
| approvalStatus           | enum [PageFeedItemApprovalStatus](./PageFeedItemApprovalStatus.md) | yes      | Kind of approval status |
| disapprovalReasonCodes[] | xsd:string                                                         | yes      | Codes of disapproval reason |
| disapprovalReasonComment | xsd:string                                                         | yes      | Comment of disapproval reason |
| pageFeedUrl              | xsd:string                                                         | yes      | Url of page feed |
| pageFeedCustomLabel      | xsd:string                                                         | yes      | Custom label of Page feed item.<br/> If multiple, comma separated. |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
