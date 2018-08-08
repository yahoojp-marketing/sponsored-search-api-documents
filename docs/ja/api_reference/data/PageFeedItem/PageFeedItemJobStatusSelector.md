# PageFeedItemJobStatusSelector

PageFeedItemJobStatusSelectorオブジェクトは、upload、downloadの処理状況を取得するための検索条件を格納します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド     | データ型                                                 | response | getJobStatus | 説明            |
|-----------|------------------------------------------------------|----------|--------------|---------------|
| accountId | xsd:long                                             | -        | Requirement  | アカウントID    |
| jobIds[]  | xsd:long                                             | -        | Optional     | 登録したジョブのID |
| jobType   | enum [PageFeedItemJobType](./PageFeedItemJobType.md) | -        | Requirement  | ジョブの種類     |
| paging    | [Paging](../Common/Paging.md)                        | -        | Optional     | ページング設定    |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
