# AdGroupAdSelector
Target ad and filter conditions which AdGroupAd to return.

### Service
+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace
[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Search condition: Account ID.</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignIds[0...1000]</td>
  <td>xsd:long</td>
  <td>Search condition: Campaign ID.<br>Ads returned will be from campaigns whose ids are included in this list. <br>An empty list means there are no campaign restrictions when selecting AdGroupAds.<br>* This field must contain distinct elements. <br>* This field cannot contain null elements. </td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupIds[0...1000]</td>
  <td>xsd:long</td>
  <td>Search condition: Ad group ID.<br>Ads returned will be from adgroups whose ids are included in this list.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adIds[0...1000]</td>
  <td>xsd:long</td>
  <td>Search condition: Ad ID.<br>Ads will return from ads whose ids are included in this list. <br>If you omit adIds field, it will return all adIds under the adGroup.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adTypes[0...4]</td>
  <td>enum <a href="AdType.md">AdType</a></td>
  <td>Search condition: Type of ad.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>userStatuses[0...2]</td>
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>Search condition: Status of ad that been set.<br>* If there is no designation, all ads in all condition will return.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatuses[0...5]</td>
  <td>enum <a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Search condition: Editorial review status.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>Search condition: Page of returned elements.</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
