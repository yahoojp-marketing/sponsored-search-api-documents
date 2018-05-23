# AccountTrackingUrl
AccountTrackingUrl object describes account tracking information.

### Service
+ [AccountTrackingUrlService](../../services/AccountTrackingUrlService.md)

### Namespace
[AccountTrackingUrlService#Namespace](../../services/AccountTrackingUrlService.md#namespace)

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
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>accountName</td>
  <td>xsd:string</td>
  <td>Account name.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL.<br>*When tag is set blank, existing Tracking URL will be deleted</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>inReviewUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL that is in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>disapprovalReviewUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL that has been disapproved.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>urlApprovalStatus</td>
  <td>enum <a href="UrlApprovalStatus.md">UrlApprovalStatus</a></td>
  <td>Review status of tracking URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes[0...n]</td>
  <td>xsd:string</td>
  <td>Code of disapproval reason.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
