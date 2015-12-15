# Keyword
Keyword object displays keyword information.

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
  <td colspan="8"><a href="./Criterion_AdGroupCriterion.md">Criterion</a>(inherited)</td>
 </tr>
 <tr>
  <td>criterionId</td>
  <td>xsd:long</td>
  <td>Criterion ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>criterionTrackId</td>
  <td>xsd:long</td>
  <td>Criterion ID for tracking.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>type</td>
  <td>enum <a href="./CriterionType.md">CriterionType</a></td>
  <td>Subtype of criteria of this instance.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td colspan="8">Keyword</td>
 </tr>
 <tr>
  <td>text</td>
  <td>xsd:string</td>
  <td>Keyword element.<br>*Maximum of 80 letters, 10 word.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>matchType</td>
  <td>enum <a href="./KeywordMatchType.md">KeywordMatchType</a></td>
  <td>match type of keyword.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
