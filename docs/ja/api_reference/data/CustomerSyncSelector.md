# CustomerSyncSelector
CustomerSyncSelectorオブジェクトは、操作履歴を取得する対象の条件を表します。
### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignIds[]| xsd:long| 対象となるキャンペーンIDです。 |
| entityType| xsd:string| 対象となるエンティティのタイプを指定します。 |
| eventTypes[]| enum <a href="../data/EventType.md">EventType</a>| 対象となる操作のタイプを指定します。 |
| sourceTypes[]| enum <a href="../data/SourceType.md">SourceType</a>| どのシステムから行われた操作かを指定します。 |
| dateRange| <a href="../data/DateRange.md">DateRange</a>| 変更状況を確認する期間を指定します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
