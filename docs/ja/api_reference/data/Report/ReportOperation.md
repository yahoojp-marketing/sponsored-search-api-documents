# ReportOperation
ReportOperationオブジェクトは、操作の対象となるレポートおよび操作の内容を表します。
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
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td colspan="8">Operation(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum Operator</td>
  <td>ADD、REMOVEが指定可能です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">ReportOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</a></td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>operand[0...20]</td>
  <td><a href="ReportRecord.md">ReportRecord</a></td>
  <td>対象レポートの配列です。<br>各配列には処理の対象となる操作対象 レポート情報が含まれます。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>


<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
