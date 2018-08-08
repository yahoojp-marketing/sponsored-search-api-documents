# PageFeedItemUploadJobStatus (enum)

PageFeedItemUploadJobStatus displays status of page feed item upload jobs.

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Enumeration                     | Type       | Description            |
|---------------------------------|------------|------------------------|
| IN_PROGRESS                     | xsd:string | Currently in progress of creating.                 |
| COMPLETED                       | xsd:string | Job has completed.                |
| COMPLETED_WITH_VALIDATION_ERROR | xsd:string | Contents written in the file are invalid. |
| FILE_FORMAT_ERROR               | xsd:string | Format of the file is invalid. |
| FILE_ENCODING_ERROR             | xsd:string | Encoding of the file is invalid. |
| COLUMN_HEADER_ERROR             | xsd:string | Content header of the file is invalid. |
| EXCEED_ROW_LINES                | xsd:string | Row count of the file exceeded the maximum. |
| EXCEED_FILE_COUNTS              | xsd:string | Count of the file exceeded the maximum. |
| INVALID_FEED_FOLDER_ID          | xsd:string | Feed folder ID is invalid. |
| TIMEOUT                         | xsd:string | Timeout |
| SYSTEM_ERROR                    | xsd:string | Systen error. |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
