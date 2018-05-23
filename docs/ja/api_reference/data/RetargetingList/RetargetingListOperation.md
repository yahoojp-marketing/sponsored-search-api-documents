# RetargetingListOperation
RetargetingListOperationは、操作対象のターゲットリストを保持するオブジェクトです。

### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

### Inheritance
+ Operation

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
  <tr>
  <td colspan="6">Operation(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum Operator</td>
  <td>ADD、SETが指定可能です。</td>
  <td colspan="3"></td>
 </tr>
 <tr>
  <td colspan="6">RetargetingListOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>owner</td>
  <td>enum <a href="TargetListOwner.md">TargetListOwner</a></td>
  <td>ターゲットリストの所有状態を表します。</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>operand[1...200]</td>
  <td><a href="TargetingList.md">TargetingList</a><br>inherited <a href="DefaultTargetList.md">DefaultTargetList</a><br>inherited <a href="RuleBaseTargetList.md">RuleBaseTargetList</a><br>inherited <a href="LogicalTargetList.md">LogicalTargetList</a></td>
  <td>操作対象ターゲットリストです。</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
