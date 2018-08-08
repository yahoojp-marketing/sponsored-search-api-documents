# PageFeedItemDownloadJobStatus (enum)

PageFeedItemDownloadJobStatusは、ページフィードアイテムダウンロードジョブの実行状況を表します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| 値            | データ型       | 説明                                  |
|--------------|------------|-------------------------------------|
| IN_PROGRESS  | xsd:string | 処理中                              |
| COMPLETED    | xsd:string | 処理完了                             |
| FIELDS_ERROR | xsd:string | ダウンロード不可能なフィールドの組み合わせを指定した場合のエラー |
| TIMEOUT      | xsd:string | タイムアウト                           |
| SYSTEM_ERROR | xsd:string | エラー                              |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
