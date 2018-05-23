# ReportRecord
ReportRecordオブジェクトは、レポートの情報を表します。
### Service
+ [ReportService](../../services/ReportService.md)

### Namespace
[ReportService#Namespace](../../services/ReportService.md#namespace)

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
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reportId</td>
  <td>xsd:long</td>
  <td>レポートIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportJobId</td>
  <td>xsd:long</td>
  <td>レポートジョブIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>レポート名称です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportJobStatus</td>
  <td>enum <a href="ReportJobStatus.md">ReportJobStatus</a></td>
  <td>レポートジョブのステータスです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportJobErrorDetail</td>
  <td>xsd:string</td>
  <td>レポートジョブのエラー詳細です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>requestTime</td>
  <td>xsd:string</td>
  <td>ジョブの起動時刻です。<br>※YYYY/MM/DD hh:mm:ss形式になります。<br>※hhは24時間表記になります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>completeTime</td>
  <td>xsd:string</td>
  <td>ジョブの完了時刻です。<br>※YYYY/MM/DD hh:mm:ss形式になります。<br>※hhは24時間表記になります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportDownloadURL</td>
  <td>xsd:string</td>
  <td>レポートファイルのダウンロード URLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
