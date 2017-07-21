# ReportRecord
ReportRecord object describes report information.
### Service
+ [ReportService](../services/ReportService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reportId</td>
  <td>xsd:long</td>
  <td>Report ID.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportJobId</td>
  <td>xsd:long</td>
  <td>Report Job ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>Name of the report.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr> 
 <tr>
  <td>reportJobStatus</td>
  <td>enum <a href="./ReportJobStatus.md">ReportJobStatus</a></td>
  <td>Status of Report Job.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportJobErrorDetail</td>
  <td>xsd:string</td>
  <td>Error details of Report Job.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>requestTime</td>
  <td>xsd:string</td>
  <td>Start time of Report Job request.<br>*Displays in YYYY/MM/DD hh:mm:ss form.<br>*hh will display in 24-hour time.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>completeTime</td>
  <td>xsd:string</td>
  <td>Completion time of Report Job request.<br>*Displays in YYYY/MM/DD hh:mm:ss form.<br>*hh will display in 24-hour time.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportDownloadURL</td>
  <td>xsd:string</td>
  <td>Download URL of report file.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
