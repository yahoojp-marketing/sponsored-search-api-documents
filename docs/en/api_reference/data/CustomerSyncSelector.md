# CustomerSyncSelector
CustomerSyncSelector object displays the conditions for the target which Operation History is obtained.
### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID. |
| campaignIds[]| xsd:long| Cmpaign ID. |
| entityType| xsd:string| Specify target entity tipe. |
| eventTypes[]| enum <a href="../data/EventType.md">EventType</a>| Specify target operation type. |
| sourceTypes[]| enum <a href="../data/SourceType.md">SourceType</a>| Specify which system operates. |
| dateRange| <a href="../data/DateRange.md">DateRange</a>| Specify the period to check change entity. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
