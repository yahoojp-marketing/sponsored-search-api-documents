# PageFeedItemDownloadJob

PageFeedItemDownloadJobオブジェクトは、ページフィードアイテム情報をダウンロードする処理内容を格納します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド                                               | データ型                                                                     | response | addDownloadJob           | 説明                         |
|-----------------------------------------------------|--------------------------------------------------------------------------|----------|--------------------------|----------------------------|
| [PageFeedItemJob](./PageFeedItemJob.md) (inherited) |                                                                          |          |                          |                            |
| encoding                                            | enum [BulkEncoding](./BulkEncoding.md)                                   | yes      | Optional<br>Default：SJIS | ページフィードアイテムファイルのエンコード形式 |
| lang                                                | enum [BulkLang](./BulkLang.md)                                           | yes      | Optional<br>Default：JA   | ページフィードアイテムファイルの言語設定    |
| output                                              | enum [BulkOutput](./BulkOutput.md)                                       | yes      | Optional<br>Default：CSV  | ダウンロードする情報の出力形式         |
| downloadJobStatus                                   | enum [PageFeedItemDownloadJobStatus](./PageFeedItemDownloadJobStatus.md) | yes      | Ignore                   | ジョブの実行状況                |
| downloadUrl                                         | xsd:string                                                               | yes      | Ignore                   | ダウンロードURL               |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
