# AdGroupCriterionOperation
AdGroupCriterionOperationオブジェクトは、操作の対象となる広告グループのクライテリアおよび操作の内容を表します。

### Service
+ [AdGroupCriterionService](../../services/AdGroupCriterionService.md)

### Namespace
[AdGroupCriterionService#Namespace](../../services/AdGroupCriterionService.md#namespace)

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
  <td>ADD、SET、REMOVEが指定可能です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">AdGroupCriterionOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>operand[1...2000]</td>
  <td><a href="AdGroupCriterion.md">AdGroupCriterion</a><br>inherited <a href="NegativeAdGroupCriterion.md">NegativeAdGroupCriterion</a><br>inherited <a href="BiddableAdGroupCriterion.md">BiddableAdGroupCriterion</a></td>
  <td>広告関係のクライテリアの配列です。<br>各配列には処理の対象となるクライテリア 情報が含まれます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
