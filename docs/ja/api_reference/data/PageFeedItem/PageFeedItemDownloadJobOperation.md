# PageFeedItemDownloadJobOperation

PageFeedItemDownloadJobOperationオブジェクトは、ページフィードアイテムを一括でダウンロードするための処理の内容を表します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド     | データ型                                                    | response | addDownloadJob | 説明                |
|-----------|---------------------------------------------------------|----------|----------------|-------------------|
| accountId | xsd:long                                                | -        | Requirement    | アカウントID        |
| operand[] | [PageFeedItemDownloadJob](./PageFeedItemDownloadJob.md) | -        | Requirement    | 登録するダウンロード処理情報 |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
