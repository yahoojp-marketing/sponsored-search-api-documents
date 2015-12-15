# ReportDefinitionReturnValue
ReportDefinitionReturnValueオブジェクトは、操作結果を含むレポート定義のコンテナです。

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
  <td colspan="8"><a href="./ListReturnValue.md">ListReturnValue</a>(inherited)</td>
 </tr>
 <tr>
  <td>ListReturnValue.Type</td>
  <td>xsd:string</td>
  <td>このインスタンスの ListReturnValue のサブタイプを示します。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>Operation.Type</td>
  <td>xsd:string</td>
  <td>mutate処理の内容です。 </td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">ReportDefinitionReturnValue</td>
 </tr>
 <tr>
  <td>values[1...30]</td>
  <td><a href="./ReportDefinitionValues.md">ReportDefinitionValues</a></td>
  <td>レポート定義詳細の配列です。各配列にはレポート定義とmutate処理の実行結果が含まれます。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
