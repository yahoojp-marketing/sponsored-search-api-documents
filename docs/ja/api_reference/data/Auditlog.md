# Auditlog
Auditlogオブジェクトは、操作履歴の情報を表します。
### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| updatedTime| xsd:string| 更新時間です。 |
| entityType| xsd:string| 変更されたエンティティのタイプです。 |
| eventType[]| enum <a href="../data/EventType.md">EventType</a>| 変更した時の操作を表します。 |
| sourceType| enum <a href="../data/SourceType.md">SourceType</a>| 変更が、どのシステムから行われたかを指定します。 |
| accountId| xsd:long| 変更されたデータのアカウントIDです。 |
| campaigneId| xsd:long| 変更されたデータのキャンペーンIDです。 |
| adGroupId| xsd:long| 変更されたデータの広告グループIDです。 |
| criterionId| xsd:long| 変更されたデータのクライテリアIDです。 |
| adId| xsd:long| 変更されたデータの広告IDです。 |
| feedItemId| xsd:long| FeedItem情報のIDです。 |
| biddingStrategyId| xsd:long| 自動入札IDです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
