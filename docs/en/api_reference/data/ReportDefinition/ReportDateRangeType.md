

# ReportDateRangeType (enum)

ReportDateRangeType displays a date range of the report.

#### Service

+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

#### Namespace

[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

| Enumeration  |       Type       |          Description          |
| ------------ | ---------------- | ----------------------------- |
| TODAY | xsd:string | Reports are generated for today only. |
| YESTERDAY | xsd:string | Reports are generated for yesterday only. |
| LAST_7_DAYS | xsd:string | Reports are generated for the last 7 days not including today. |
| LAST_WEEK | xsd:string | Reports are generated for the 7 day period, starting from previous Monday. |
| LAST_14_DAYS | xsd:string | Reports are generated for the last 14 days, not including today. |
| LAST_30_DAYS | xsd:string | Reports are generated for the last 30 days, not including today. |
| LAST_BUSINESS_WEEK | xsd:string | Reports are generated for the 5 business day, starting from previous Monday. |
| THIS_MONTH | xsd:string | Reports are generated for all days of current month. |
| LAST_MONTH | xsd:string | Reports are generated for all days of previous month. |
| ALL_TIME | xsd:string | Reports are generated for all available time range. |
| CUSTOM_DATE | xsd:string | Reports are generated for specified date range.<br/>Specific date must be input through DateRange. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
