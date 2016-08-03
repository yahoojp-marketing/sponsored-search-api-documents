# DateRange
DateRange object displays the conditions and period to get Operation History.

### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>Start date of target date.<br>*1-3<br></td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>End date of target date.<br>*1-3</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>
*1 For CustomerSyncService, please set in YYYYMMDDhhmmss format. You can specify up to second unit. <br>
　(Example) To set the time/date as May 25th, 2016 02:05:35PM: 20160525140535<br>
　(Default will be 0:00:00, if time is not set)<br>
*2 For ReportDefinitionService, please set in YYYYMMDD format.<br>
*3 Can set the date between 19700101 - 20371231.<br>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
