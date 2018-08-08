# PageFeedItemReviewSummary

PageFeedItemReviewSummaryオブジェクトは、ページフィードアイテムの審査成績、状況サマリーを格納します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド                   | データ型     | 説明                             |
|-------------------------|----------|--------------------------------|
| accountId               | xsd:long | アカウントID                     |
| feedFolderId            | xsd:long | フィードフォルダID                  |
| entityCount             | xsd:long | フィードフォルダ内にあるページフィードアイテムの総件数 |
| approvedCount           | xsd:long | 承認済みの件数                     |
| approvedWithReviewCount | xsd:long | 編集内容審査中の件数                  |
| reviewCount             | xsd:long | 審査中の件数                      |
| preDisapprovedCount     | xsd:long | 掲載不可の件数                     |
| postDisapprovedCount    | xsd:long | 配信停止の件数                     |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
