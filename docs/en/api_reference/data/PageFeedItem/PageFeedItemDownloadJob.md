# PageFeedItemDownloadJob
PageFeedItemDownloadJob object retains contents of page feed item information for download.

### Service
- [PageFeedItemService](../../services/PageFeedItemService.md)

### Namespace
[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field | Type | response | addDownloadJob | Description |
|---|---|---|---|---|
| [PageFeedItemJob](./PageFeedItemJob.md) (inherited) |||||
| encoding | enum [BulkEncoding](./BulkEncoding.md) | yes | Optional<br>Default：SJIS | Encoding format of page feed item |
| lang | enum [BulkLang](./BulkLang.md) | yes | Optional<br>Default：JA | Language setting of page feed item file |
| output | enum [BulkOutput](./BulkOutput.md) | yes | Optional<br>Default：CSV | Output format of download information |
| downloadJobStatus | enum [PageFeedItemDownloadJobStatus](./PageFeedItemDownloadJobStatus.md) | yes | Ignore | Execution status of job |
| downloadUrl | xsd:string | yes | Ignore | Download URL |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
