# ReportRecord
ReportRecordオブジェクトは、レポートの情報を表します。
### Service
+ [ReportService](../services/ReportService.md)

| フィールド | データ型 | 説明 | ADD | REMOVE | 
|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| ─| ─ |
| reportJobId| xsd:long| ジョブIDです。| ─| Req |
| reportId| xsd:long| レポート定義IDです。| Req| ─ |
| reportname| xsd:string| レポート名です。| ─| ─ |
| requestTime| xsd:long| ジョブの起動時刻です。| ─| ─ |
| completeTime| xsd:long| ジョブの完了時刻です。| ─| ─ |
| dateRangeType| enum <a href="../data/ReportDateRangeType.md">ReportDateRangeType</a>| 集計対象期間を表します。| ─| ─ |
| dateRange| <a href="../data/ReportDateRange.md">ReportDateRange</a>| レポートの集計対象期間です。| ─| ─ |
| status| enum <a href="../data/ReportJobStatus.md">ReportJobStatus</a>| レポートの処理状況です。| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
