# PageFeedItemUploadJob

PageFeedItemUploadJobオブジェクトは、ページフィードアイテム情報をダウンロードする処理内容を格納します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド                                               | データ型                                                                 | 説明               |
|-----------------------------------------------------|----------------------------------------------------------------------|------------------|
| [PageFeedItemJob](./PageFeedItemJob.md) (inherited) |                                                                      |                  |
| uploadJobStatus                                     | enum [PageFeedItemUploadJobStatus](./PageFeedItemUploadJobStatus.md) | ジョブの実行状況         |
| errorCount                                          | xsd:int                                                              | エラーの件数           |
| errorFileUrl                                        | xsd:string                                                           | エラーファイルダウンロードURL |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
