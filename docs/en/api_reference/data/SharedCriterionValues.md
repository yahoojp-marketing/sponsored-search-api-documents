# SharedCriterionValues
SharedCriterionValues object holds exec result (1 entity) of get/mutate method.

### Service
+ [SharedCriterionService](../services/SharedCriterionService.md)

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
  <td>Showing operation result.</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>error[0...n]</td>
  <td><a href="./Error.md">Error</a></td>
  <td>Error detail.</td>
  <td colspan="7"></td>
 </tr>
 <tr>
  <td colspan="8">SharedCriterionValues</td>
 </tr>
 <tr>
  <td>sharedCriterion</td>
  <td><a href="./SharedCriterion.md">SharedCriterion</a></td>
  <td>Execution result of get/mutate method per single negative keyword. </td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
