# ReportDefinitionOperation
ReportDefinitionOperationオブジェクトは、操作の対象となるレポート定義および操作の内容を表します。

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
  <td colspan="8"><a href="./Operation.md">Operation</a>(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum <a href="./Operator.md">Operator</a></td>
  <td>処理を表す演算子です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">ReportDefinitionOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>operand[1...30]</td>
  <td><a href="./ReportDefinition.md">ReportDefinition</a></td>
  <td>レポート定義の配列です。<br>各配列には処理の対象となる レポート定義情報が含まれます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
