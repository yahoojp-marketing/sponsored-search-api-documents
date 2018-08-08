# PageFeedItemJobStatusSelector

PageFeedItemJobStatusSelector object retains search condition for The processing situation upload/download.

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field     | Data                                                 | response | getJobStatus | Description   |
|-----------|------------------------------------------------------|----------|--------------|---------------|
| accountId | xsd:long                                             | -        | Requirement  | Account ID    |
| jobIds[]  | xsd:long                                             | -        | Optional     | Registered job ID |
| jobType   | enum [PageFeedItemJobType](./PageFeedItemJobType.md) | -        | Requirement  | Kind of job     |
| paging    | [Paging](../Common/Paging.md)                        | -        | Optional     | setting of paging |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
