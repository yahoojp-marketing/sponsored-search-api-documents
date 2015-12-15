# TargetingIdeaPage
TargetingIdeaPageオブジェクトは、関連キーワードの結果を格納するコンテナです。

### Service
+ [TargetingIdeaService](../services/TargetingIdeaService.md)

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
  <td colspan="8"><a href="./Page.md">Page</a>(inherited)</td>
 </tr>
 <tr>
  <td>totalNumEntries</td>
  <td>xsd:int</td>
  <td>取得される項目の総件数です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>Page.Type</td>
  <td>xsd:string</td>
  <td>このインスタンスのPage のサブタイプです。 </td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">RetargetingListPage</td>
 </tr>
 <tr>
  <td>values[0...n]</td>
  <td><a href="./TargetingIdeaValues.md">TargetingIdeaValues</a></td>
  <td>提案結果の配列です。<br>各配列にはget操作結果および 提案情報が含まれます。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
