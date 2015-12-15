# FeedItem
FeedItem is a container of Feed Item information.

### Service
+ [FeedItemService](../services/FeedItemService.md)

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
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedFolderId</td>
  <td>xsd:long</td>
  <td>Feed Folder ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>*Requirement for Data Auto Insertion.</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedItemId</td>
  <td>xsd:long</td>
  <td>Feed Item ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>feedItemTrackId</td>
  <td>xsd:long</td>
  <td>Feed Item ID for tracking.<br>* "0" will return in Sandbox.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatus</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Review status.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes[0...n]</td>
  <td>xsd:string</td>
  <td>Code of Disapproval reason.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedItemAttribute[0...20]</td>
  <td><a href="./FeedItemAttribute.md">FeedItemAttribute</a></td>
  <td>Attribute of Feed Item.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>placeholderType</td>
  <td>enum <a href="./PlaceholderType_FeedItem.md">PlaceholderType</a></td>
  <td>Type of Feed Item.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>devicePreference</td>
  <td>enum <a href="./DevicePreference.md">DevicePreference</a></td>
  <td>Appoint the high priority device in delivering ads.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>* Optional for Call Extension<br>* Default: SMART_PHONE</td>
  <td>Optional<br>* Ignore for Call Extension.</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>Start date of ad display.<br>* To deactivate, set it blank.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>End date of ad display.<br>* To deactivate, set it blank.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>scheduling</td>
  <td><a href="./FeedItemScheduling.md">FeedItemScheduling</a></td>
  <td>Ad display schedule.<br>* To deactivate, set it blank.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingCampaign</td>
  <td><a href="./TargetingCampaign.md">TargetingCampaign</a></td>
  <td>Campaign used for Feed Item.</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>* Requirement for Data Auto Insertion</td>
  <td>-<br>* Requirement for Data Auto Insertion</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingAdGroup</td>
  <td><a href="./TargetingAdGroup.md">TargetingAdGroup</a></td>
  <td>Ad group used for Feed Item.</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>* Optional for Data Auto Insertion</td>
  <td>-<br>* Optional for Data Auto Insertion</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingKeyword</td>
  <td><a href="./TargetingKeyword.md">TargetingKeyword</a></td>
  <td>Keyword used for Feed Item.</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>* Optional for Data Auto Insertion</td>
  <td>-<br>* Optional for Data Auto Insertion</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>Custom parameters.</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>* Optional for Quick Link</td>
  <td>-<br>* Optional for Quick Link</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reviewCustomParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>Custom parameters in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advanced</td>
  <td>enum <a href="./Advanced.md">Advanced</a></td>
  <td>Keyword used for Feed Item.</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>* Optional for Quick Link<br>* Default: TRUE</td>
  <td>-<br>* Optional for Quick Link<br>* Default: TRUE</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
