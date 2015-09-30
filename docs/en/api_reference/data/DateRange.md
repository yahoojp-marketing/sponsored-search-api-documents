# DateRange
DateRange object displays the conditions and period to get Operation History.
### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)

| Field | Data Type | Description | 
|---|---|---|
| startDate| xsd:string| Start date of target date. <br>It will specified as 0:00:00, if there is no setting in time (It can be specified on the second bit). |
| endDate| xsd:string| End date of target date. <br>It will specified as 0:00:00, if there is no setting in time (It can be specified on the second bit). |
| includeUnset| enum <a href="../data/IncludeUnset.md">IncludeUnset</a>| Specify whether include unspecified date for status change. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
