# ReportDateRangeType (enum)
ReportDateRangeTypeは、レポートの集計対象期間を表します。
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)
+ [ReportService](../services/ReportService.md)

| 値 | データ型 | 説明 | 
|---|---|---|
| TODAY| string| 本日です。 |
| YESTERDAY| string| 昨日です。 |
| LAST_7_DAYS| string| 本日を除く、過去7日間です。 |
| LAST_WEEK| string| 先週の月曜日から日曜日です。 |
| LAST_14_DAYS| string| 本日を除く、過去14日間です。 |
| LAST_30_DAYS| string| 本日を除く、過去30日間です。 |
| LAST_BUSINESS_WEEK| string| 先週の月曜日から5営業日です。 |
| THIS_MONTH| string| 本日を含む、当月です。 |
| LAST_MONTH| string| 前月です。 |
| ALL_TIME| string| 取得可能な全期間です。 |
| CUSTOM_DATE| string| ユーザーにより指定される期間です。<br>CUSTOM_DATEを指定した場合、集計対象期間の指定が必要です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
