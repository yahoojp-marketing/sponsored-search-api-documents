# AccountSharedOperation
AccountSharedOperationオブジェクトは、mutateメソッドで操作対象となるアカウント情報と処理の内容を表します。

### Service
+ [AccountSharedService](../../services/AccountSharedService.md)

### Namespace
[AccountSharedService#Namespace](../../services/AccountSharedService.md#namespace)

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
  <td>enum <br>
  Operator</td>
  <td>ADD、SET、REMOVEが指定可能です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">AccountSharedOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>operand[1..20]</td>
  <td><a href="AccountShared.md">AccountShared</a></td>
  <td>操作対象となる対象外 キーワードリストです。</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

