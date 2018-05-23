# SharedCriterionPage
SharedCriterionPageオブジェクトは、getメソッドの検索結果（全エンティティのリスト）を保持します。
### Service
+ [SharedCriterionService](../../services/SharedCriterionService.md)

### Namespace
[SharedCriterionService#Namespace](../../services/SharedCriterionService.md#namespace)

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
  <td colspan="8"><a href="../Common/Page.md">Page</a>(inherited)</td>
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
  <td>このインスタンスのPageのサブタイプです。 </td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">SharedCriterionPage</td>
 </tr>
 <tr>
  <td>values[0..1000]</td>
  <td><a href="SharedCriterionValues.md">SharedCriterionValues</a></td>
  <td>getメソッドの実行結果です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
