# PageFeedItemJob

PageFeedItemJobオブジェクトは、ジョブの処理状況を格納します。

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| フィールド           | データ型       | response | addDownloadJob | 説明            |
|-----------------|------------|----------|----------------|---------------|
| accountId       | xsd:long   | yes      | Requirement    | アカウントID    |
| jobId           | xsd:long   | yes      | Ignore         | ジョブID      |
| feedFolderIds[] | xsd:long   | yes      | Requirement    | フィードフォルダID |
| progress        | xsd:int    | yes      | Ignore         | ジョブの進捗状況   |
| startDate       | xsd:string | yes      | Ignore         | ジョブの開始日<br>形式：yyyyMMddHHmmss    |
| endDate         | xsd:string | yes      | Ignore         | ジョブの終了日<br>形式：yyyyMMddHHmmss    |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
