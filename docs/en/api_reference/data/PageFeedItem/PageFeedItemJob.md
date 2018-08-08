# PageFeedItemJob

PageFeedItemJob retains progress of page feed item job.


## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field           | Data       | response | addDownloadJob | Description   |
|-----------------|------------|----------|----------------|---------------|
| accountId       | xsd:long   | yes      | Requirement    | Account ID    |
| jobId           | xsd:long   | yes      | Ignore         | Job ID      |
| feedFolderIds[] | xsd:long   | yes      | Requirement    | Feed folder ID |
| progress        | xsd:int    | yes      | Ignore         | Progress of page feed item job  |
| startDate       | xsd:string | yes      | Ignore         | Start date of job <br>Format:yyyyMMddHHmmss|
| endDate         | xsd:string | yes      | Ignore         | End date of job <br>Format:yyyyMMddHHmmss|

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
