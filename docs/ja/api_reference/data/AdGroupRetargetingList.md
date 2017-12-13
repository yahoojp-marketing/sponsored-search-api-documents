# AdGroupRetargetingList
AdGroupRetargetingListは、広告グループレベルでのターゲットリスト設定を保持するオブジェクトです。

### Service
+ [AdGroupRetargetingListService](../services/AdGroupRetargetingListService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>ignore</td>
  <td>ignore</td>
  <td>ignore</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名です。</td>
  <td>yes</td>
  <td>ignore</td>
  <td>ignore</td>
  <td>ignore</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>広告グループIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>広告グループ名です。</td>
  <td>yes</td>
  <td>ignore</td>
  <td>ignore</td>
  <td>ignore</td>
 </tr>
 <tr>
  <td>criterionTargetList</td>
  <td><a href="./CriterionTargetList.md">CriterionTargetList</a></td>
  <td>ターゲットリストです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>excludedType</td>
  <td>enum <a href="./ExcludedType.md">ExcludedType</a></td>
  <td>包含/追加設定です。<br>※Default値：INCLUDED</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>bidMultiplier</td>
  <td>xsd:double</td>
  <td>MaxCPC上昇値です。<br>※Default値：1.00 </td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
