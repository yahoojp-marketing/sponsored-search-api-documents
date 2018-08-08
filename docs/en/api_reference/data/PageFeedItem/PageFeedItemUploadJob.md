# PageFeedItemUploadJob
PageFeedItemUploadJob object retains contents of page feed item information for upload.

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field                                               | Type                                                                 | Description               |
|-----------------------------------------------------|----------------------------------------------------------------------|------------------|
| [PageFeedItemJob](./PageFeedItemJob.md) (inherited) |                                                                      |                  |
| uploadJobStatus                                     | enum [PageFeedItemUploadJobStatus](./PageFeedItemUploadJobStatus.md) | Execution status of job |
| errorCount                                          | xsd:int                                                              | count of error occured |
| errorFileUrl                                        | xsd:string                                                           | Download url of error file |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
