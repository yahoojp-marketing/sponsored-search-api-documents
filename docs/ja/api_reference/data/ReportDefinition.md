# ReportDefinition
ReportDefinitionオブジェクトは、レポート定義を表します。
### Service
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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportId</td>
  <td>xsd:long</td>
  <td>レポートIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>reportName</td>
  <td>xsd:string</td>
  <td>レポート名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reportType</td>
  <td>enum <a href="./ReportType.md">ReportType</a></td>
  <td>レポートの種類です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>dateRangeType</td>
  <td>enum <a href="./ReportDateRangeType.md">ReportDateRangeType</a></td>
  <td>定義されたレポートの集計対象期間です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="./DateRange.md">DateRange</a></td>
  <td>ユーザーにより設定されるレポート集計の範囲期間です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>fields[1...100]</td>
  <td>xsd:string</td>
  <td>フィールド（レポートの出力項目名）です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>sortFields[0...1]</td>
  <td><a href="./ReportSortField.md">ReportSortField</a></td>
  <td>フィールド名を指定し、ソートします。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>filters[0...6]</td>
  <td><a href="./ReportFilter.md">ReportFilter</a></td>
  <td>レポートのフィルタ条件です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>isTemplate</td>
  <td>enum <a href="./ReportIsTemplate.md">ReportIsTemplate</a></td>
  <td>テンプレートの有無を選択します。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>intervalType</td>
  <td>enum <a href="./ReportIntervalType.md">ReportIntervalType</a></td>
  <td>定期レポート作成タイミング設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>specifyDay</td>
  <td>xsd:int</td>
  <td>定期レポート作成日の設定です。<br>※1～31の日付を指定できます。<br>※毎月初は「1」、毎月末は「31」と指定してください。<br>※intervalType：SPECIFYDAYの場合のみ有効です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>format</td>
  <td>enum <a href="./ReportDownloadFormat.md">ReportDownloadFormat</a></td>
  <td>定義されたダウンロードレポートのファイル形式です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>encode</td>
  <td>enum <a href="./ReportDownloadEncode.md">ReportDownloadEncode</a></td>
  <td> 定義されたダウンロードレポートの文字コードです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>language</td>
  <td>enum <a href="./ReportLanguage.md">ReportLanguage</a></td>
  <td>レポート定義の出力言語です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>compress</td>
  <td>enum <a href="./ReportCompressType.md">ReportCompressType</a></td>
  <td>レポート定義の圧縮形式での出力です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
