# AdGroupCriterionOperation
AdGroupCriterionOperation displays target ad group criteria information and its operation results.

### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

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
  <td colspan="8"><a href="./Operation.md">Operation</a>(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum <a href="./Operator.md">Operator</a></td>
  <td>Operator that displays process.</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">AdGroupCriterionOperation</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>operand[1...2000]</td>
  <td><a href="./AdGroupCriterion.md">AdGroupCriterion</a><br>inherited <a href="./NegativeAdGroupCriterion.md">NegativeAdGroupCriterion</a><br>inherited <a href="./BiddableAdGroupCriterion.md">BiddableAdGroupCriterion</a></td>
  <td>List of ad related criterion.<br>Each list includes details of criterion.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
