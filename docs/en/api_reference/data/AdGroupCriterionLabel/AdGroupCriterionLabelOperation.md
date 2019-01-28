# AdGroupCriterionLabelOperation
AdGroupCriterionLabelOperation displays information of ad group criterion label to be operated and processing content.
### Service
+ [AdGroupCriterionLabelService](../../services/AdGroupCriterionLabelService.md)

### Namespace
[AdGroupCriterionLabelService#Namespace](../../services/AdGroupCriterionLabelService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>remove</th>
 </tr>
 <tr>
  <td colspan="6">Operation(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum Operator</td>
  <td>ADD or REMOVE</td>
  <td colspan="3"></td>
 </tr>
 <tr>
  <td colspan="6">AdGroupCriterionLabelOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
  <tr>
  <td>operand[1...2000]</td>
  <td><a href="AdGroupCriterionLabel.md">AdGroupCriterionLabel</a></td>
  <td>Array of Ad group criterion label<br>&lowast;Each array includes the details of Ad group criterion label.</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
