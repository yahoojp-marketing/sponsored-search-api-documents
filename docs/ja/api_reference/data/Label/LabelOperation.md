# LabelOperation
LabelOperationオブジェクトは、操作の対象となるラベルの情報と処理の内容を表します。

### Service
+ [LabelService](../../services/LabelService.md)

### Namespace
[LabelService#Namespace](../../services/LabelService.md#namespace)

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
  <td colspan="10">Operation(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum Operator</td>
  <td>ADD or SET or REMOVE</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="10">LabelOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントID</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
  <tr>
  <td>operand[1...2000]</td>
  <td><a href="Label.md">Label</a></td>
  <td>ラベルの配列<br>(各配列には処理の対象となるラベルの情報が含まれる)</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
