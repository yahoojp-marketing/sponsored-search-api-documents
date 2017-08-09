# AuditLogJob
AuditLogJob object retains the job information to be added for getting operation history data.
  
### Service
+ [AuditLogService](../services/AuditLogService.md)
 
<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>addJob</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>jobId</td>
  <td>xsd:long</td>
  <td>Job ID.</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>jobName</td>
  <td>xsd:string</td>
  <td>Name of job.</td>
  <td>yes</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>jobStatus</td>
  <td>enum<br><a href="./AuditLogJobStatus.md">AuditLogJobStatus</a></td>
  <td>Status of job executed.</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>downloadUrl</td>
  <td>xsd:string</td>
  <td>The download URL for operation history data file. <br>*It returns when the jobStatus is 'COMPLETED'.</td>
  <td>yes</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>eventSelector[1..25]</td>
  <td><a href="./EventSelector.md">EventSelector</a></td>
  <td>Operation history data to be acquired by the operation.</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="./DateRange.md">DateRange</a></td>
  <td>Date range of targeted operation history data.</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>sourceType</td>
  <td>enum<br><a href="./AuditLogSourceType.md">AuditLogSourceType</a></td>
  <td>Operator.</td>
  <td>yes</td>
  <td>Optional<br>Default：API</td>
 </tr>
 <tr>
  <td>output</td>
  <td>enum<br><a href="./AuditLogOutput.md">AuditLogOutput</a></td>
  <td>Output format of operation history data file.</td>
  <td>yes</td>
<td>Optional<br>Default：CSV</td>
 </tr>
 <tr>
  <td>encoding</td>
  <td>enum<br><a href="./AuditLogEncoding.md">AuditLogEncoding</a></td>
  <td>Encoding type of operation history data file.</td>
  <td>yes</td>
<td>Optional<br>Default：SJIS</td>
 </tr>
 <tr>
  <td>lang</td>
  <td>enum<br><a href="./AuditLogLang.md">AuditLogLang</a></td>
  <td>Language setting of operation history data file.</td>
    <td>yes</td>
  <td>Optional<br>Default：JA</td>
 </tr>
 </table>
   
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
