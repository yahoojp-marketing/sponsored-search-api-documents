

# ReportDefinition

ReportDefinitionオブジェクトは、レポートの情報を表します。

### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Field | Type | Description | response | getReportFields | get | add | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | - | - | - | - | |
| reportJobId | xsd:long | レポートジョブIDです。 | yes | - | - | - | Requirement | |
| reportJobStatus | enum [ReportJobStatus](./ReportJobStatus.md) | レポートジョブのステータスです。 | yes | - | - | - | - | |
| reportJobErrorDetail | xsd:string | レポートジョブのエラー詳細です。 | yes | - | - | - | - | |
| requestTime | xsd:string | ジョブの起動時刻です。<br/>※YYYY/MM/DD hh:mm:ss形式になります。<br/>※hhは24時間表記になります。 | yes | - | - | - | - | |
| completeTime | xsd:string | ジョブの完了時刻です。<br/>※YYYY/MM/DD hh:mm:ss形式になります。<br/>※hhは24時間表記になります。 | yes | - | - | - | - | |
| reportDownloadURL | xsd:string | レポートファイルのダウンロード URLです。 | yes | - | - | - | - | |
| reportName | xsd:string | レポート名称です。 | yes | - | - | Requirement | - | |
| reportType | enum [ReportType](./ReportType.md) | レポートの種類です。 | yes | - | - | Requirement | - | |
| dateRangeType | enum [ReportDateRangeType](./ReportDateRangeType.md) | レポートの集計対象期間です。 | yes | - | - | Requirement | - | |
| dateRange | [ReportDateRange](./ReportDateRange.md) | ユーザーにより設定されるレポート集計の範囲期間です。 | yes | - | - | Optional | - | |
| fields[1...100] | xsd:string | フィールド（レポートの出力項目名）です。 | yes | - | - | Requirement | - | |
| sortFields[0...1] | [ReportSortField](./ReportSortField.md) | フィールド名を指定し、ソートします。 | yes | - | - | Optional | - | |
| filters[0...6] | [ReportFilter](./ReportFilter.md) | レポートのフィルタ条件です。 | yes | - | - | Optional | - | |
| format | enum [ReportDownloadFormat](./ReportDownloadFormat.md) | ダウンロードレポートのファイル形式です。<br/>※Default：CSV | yes | - | - | Optional | - | |
| encode | enum [ReportDownloadEncode](./ReportDownloadEncode.md) | ダウンロードレポートの文字コードです。<br/>※Default：UTF-8 | yes | - | - | Optional | - | |
| language | enum [ReportLanguage](./ReportLanguage.md) | レポートの出力言語です。<br/>※Default：JA（日本語） | yes | - | - | Optional | - | |
| compress | enum [ReportCompressType](./ReportCompressType.md) | レポートを圧縮して出力するかを選択します。<br/>※Default：NONE（圧縮しない） | yes | - | - | Optional | - | |
| includeZeroImpressions | enum [ReportIncludeZeroImpressions](./ReportIncludeZeroImpressions.md) | 0インプレッションの行をレポートに含めるかを選択します。<br/>※Default：FALSE（含めない） | yes | - | - | Optional | - | |
| includeDeleted | enum [ReportIncludeDeleted](./ReportIncludeDeleted.md) | 削除済みの項目を出力対象にするかを選択します。<br/>FALSEを指定した場合は、削除済み、および掲載停止の項目が出力対象外になります。<br/>※Default：TRUE（出力対象）<br/> | yes | - | - | Optional<br/>※レポートタイプが以下の場合のみ。<br/>・CAMPAIGN<br/>・ADGROUP<br/>・AD<br/>・KEYWORDS<br/>・FEED_ITEM<br/>・AD_CUSTOMIZERS<br/>これ以外の場合はIgnore | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
