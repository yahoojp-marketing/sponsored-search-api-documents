# UrlRuleItem
UrlRuleItem is an object that holds evaluation of URL rules.

### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

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
  <td colspan="8"><a href="RuleItem.md">RuleItem</a>(inherited)</td>
 </tr>
 <tr>
  <td>ruleType</td>
  <td>enum <a href="RuleType.md">RuleType</a></td>
  <td>Type of evaluation condition.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum <a href="RuleOperator.md">RuleOperator</a></td>
  <td>Evaluation type.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>value</td>
  <td>xsd:string</td>
  <td>Evaluation value.<br>*Cannot use: bracket, single quote, double quote, and tab.<br>*Can select up to 250 characters. </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
  <tr>
  <td colspan="8">UrlRuleItem</td>
 </tr>
  <tr>
  <td>urlKey</td>
  <td>enum <a href="UrlRuleKey.md">UrlRuleKey</a></td>
  <td>Evaluation items (for URL / Refer URL).</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
