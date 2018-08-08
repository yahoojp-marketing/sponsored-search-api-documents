# PageFeedItem

PageFeedItemオブジェクトは、ページフィードアイテム情報を格納します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド                    | データ型                                                               | response | 説明                                     |
|--------------------------|--------------------------------------------------------------------|----------|----------------------------------------|
| accountId                | xsd:long                                                           | yes      | アカウントID                                |
| feedFolderId             | xsd:long                                                           | yes      | フィードフォルダID                             |
| pageFeedItemId           | xsd:long                                                           | yes      | ページフィードアイテムID                          |
| approvalStatus           | enum [PageFeedItemApprovalStatus](./PageFeedItemApprovalStatus.md) | yes      | 審査ステータスの種類                             |
| disapprovalReasonCodes[] | xsd:string                                                         | yes      | 審査否認理由コード                              |
| disapprovalReasonComment | xsd:string                                                         | yes      | 審査否認理由のコメント                            |
| pageFeedUrl              | xsd:string                                                         | yes      | ページフィードURL。                            |
| pageFeedCustomLabel      | xsd:string                                                         | yes      | ページフィードアイテムのカスタムラベル<br/> 複数ある場合はカンマ区切り |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
