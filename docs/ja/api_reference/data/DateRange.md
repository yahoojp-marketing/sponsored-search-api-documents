# DateRange
DataRangeオブジェクトは操作履歴を取得する条件、期間を示します。
### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| startDate| xsd:string| 対象期間の開始日時です。<br>時間の指定がない場合、0:00:00として指定されます（秒単位まで指定が可能です）。 |
| endDate| xsd:string| 対象期間の終了日時です。<br>時間の指定がない場合、0:00:00として指定されます（秒単位まで指定が可能です）。 |
| includeUnset| enum <a href="../data/IncludeUnset.md">IncludeUnset</a>| 変更状況の日時が設定されていないデータも含めるか指定します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
