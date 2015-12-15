# RetargetingListValues
RetargetingListValuesは、ターゲットリストのget/mutateメソッドの実行結果（1 Entity）を保持するオブジェクトです。。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

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
  <td colspan="8"><a href="./ReturnValue.md">ReturnValue</a>(inherited)</td>
 </tr>
 <tr>
  <td>operationSucceeded</td>
  <td>xsd:boolean</td>
  <td>処理結果を表示します。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>error[0...n]</td>
  <td><a href="./Error.md">Error</a></td>
  <td>エラーの内容です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">RetargetingListValues</td>
 </tr>
 <tr>
  <td>targetList</td>
  <td><a href="./TargetingList.md">TargetingList</a><br>inherited <a href="./DefaultTargetList.md">DefaultTargetList</a><br>inherited <a href="./RuleBaseTargetList.md">RuleBaseTargetList</a><br>inherited <a href="./LogicalTargetList.md">LogicalTargetList</a></td>
  <td>get/mutateメソッドの実行結果です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
