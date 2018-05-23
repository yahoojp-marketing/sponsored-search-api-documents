# UrlRuleItem
UrlRuleItemは、URLルールの評価式を保持するオブジェクトです。

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
  <td>評価条件の種別です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum <a href="RuleOperator.md">RuleOperator</a></td>
  <td>評価式です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>value</td>
  <td>xsd:string</td>
  <td>評価値です。<br>※括弧（()）、シングルクォート（'）、ダブルクォート（"）、タブ（\t）は利用できません。<br>※250文字まで指定可能です。 </td>
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
  <td>評価項目です（URL/リファラURL）。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
