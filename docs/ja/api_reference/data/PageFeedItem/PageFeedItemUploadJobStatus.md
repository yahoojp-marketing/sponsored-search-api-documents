# PageFeedItemUploadJobStatus (enum)

PageFeedItemUploadJobStatusは、ページフィードアイテムアップロードジョブの実行状況を表します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Enumeration                     | Type | Description                  |
|---------------------------------|------------|------------------------|
| IN_PROGRESS                     | xsd:string | 処理中                 |
| COMPLETED                       | xsd:string | 処理完了                |
| COMPLETED_WITH_VALIDATION_ERROR | xsd:string | ファイル内の入力値が不正        |
| FILE_FORMAT_ERROR               | xsd:string | ファイルのフォーマットが不正      |
| FILE_ENCODING_ERROR             | xsd:string | ファイルのエンコードが不正       |
| COLUMN_HEADER_ERROR             | xsd:string | ファイルのヘッダーが不正        |
| EXCEED_ROW_LINES                | xsd:string | ファイルの最大行数が超過しています。     |
| EXCEED_FILE_COUNTS              | xsd:string | 複数のファイルを圧縮しているためエラー |
| INVALID_FEED_FOLDER_ID          | xsd:string | フィードフォルダIDが不正       |
| TIMEOUT                         | xsd:string | タイムアウト              |
| SYSTEM_ERROR                    | xsd:string | エラー                 |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
