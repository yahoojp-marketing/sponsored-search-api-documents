# PageFeedItemSelector

PageFeedItemSelectorオブジェクトは、登録したページフィードアイテムを照会するための検索条件を格納します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド               | データ型                                                               | response | get         | 説明                |
|---------------------|--------------------------------------------------------------------|----------|-------------|-------------------|
| accountId           | xsd:long                                                           | -        | Requirement | アカウントID        |
| feedFolderIds[]     | xsd:long                                                           | -        | Requirement | フィードフォルダID     |
| approvalStatuses[]  | enum [PageFeedItemApprovalStatus](./PageFeedItemApprovalStatus.md) | -        | Optional    | 審査ステータスの種類     |
| pageFeedUrl[]       | [PageFeedUrl](./PageFeedUrl.md)                                    | -        | Optional    | ページフィードURL検索条件 |
| pageFeedCustomLabel | xsd:string                                                         | -        | Optional    | カスタムラベル        |
| paging              | [Paging](../Common/Paging.md)                                      | -        | Optional    | ページング設定        |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
