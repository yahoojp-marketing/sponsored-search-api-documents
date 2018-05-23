# FeedItem
FeedItem object contains the information of Feed Item.

### Service
+ [FeedItemService](../../services/FeedItemService.md)

### Namespace
[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

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
  <td>Account ID</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedFolderId</td>
  <td>xsd:long</td>
  <td>Feed Folder ID</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>&lowast;Required only in Ad Customizer</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedItemId</td>
  <td>xsd:long</td>
  <td>Feed Item ID</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Required</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>feedItemTrackId</td>
  <td>xsd:long</td>
  <td>Feed Item ID for tracking<br>&lowast;In Sandbox,"0" will return.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatus</td>
  <td>enum <a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Review status</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes[0...n]</td>
  <td>xsd:string</td>
  <td>Reject reason on editorial review</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedItemAttribute[0...20]</td>
  <td><a href="FeedItemAttribute.md">FeedItemAttribute</a><br>
  inherited<br>
  <a href="SimpleFeedItemAttribute.md">SimpleFeedItemAttribute</a><br>
  <a href="MultipleFeedItemAttribute.md">MultipleFeedItemAttribute	</a><br>
  </td>
  <td>Attribute of Feed Item</td>
  <td>yes</td>
  <td>-</td>
  <td>Required</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>placeholderType</td>
  <td>enum <a href="FeedItemPlaceholderType.md">FeedItemPlaceholderType</a></td>
  <td>Type of Feed Item</td>
  <td>yes</td>
  <td></td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>devicePreference</td>
  <td>enum <a href="DevicePreference.md">DevicePreference</a></td>
  <td>The settings of Focus Device<br>&lowast;On setting blank, existing focus device setting will be deleted (excluding Call Extension).</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>&lowast;Optional for Call Extension<br>&lowast;Default: SMART_PHONE</td>
  <td>Optional<br>&lowast;Ignore for Call Extension</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>Start date of ad display<br>&lowast;On setting blank, existing start date of ad display will be deleted</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>End date of ad display<br>&lowast;On setting blank, existing end date of ad display will be deleted</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>scheduling</td>
  <td><a href="FeedItemScheduling.md">FeedItemScheduling</a></td>
  <td>Ad display schedule<br>&lowast;On setting blank, existing ad display schedule will be deleted</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingCampaign</td>
  <td><a href="TargetingCampaign.md">TargetingCampaign</a></td>
  <td>Campaign used for Ad Customizer</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>&lowast;Optional for Ad Customizer</td>
  <td>-<br>&lowast;Optional for Ad Customizer</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingAdGroup</td>
  <td><a href="TargetingAdGroup.md">TargetingAdGroup</a></td>
  <td>Ad Group used for Ad Customizer</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>&lowast;Optional for Ad Customizer</td>
  <td>-<br>&lowast;Optional for Ad Customizer</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingKeyword</td>
  <td><a href="TargetingKeyword.md">TargetingKeyword</a></td>
  <td>Keyword used for Ad Customizer</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>&lowast;Optional for Ad Customizer</td>
  <td>-<br>&lowast;Optional for Ad Customizer</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>Custom parameters</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>&lowast;Optional for QuickLinks</td>
  <td>-<br>&lowast;Optional for QuickLinks</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reviewCustomParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>Custom parameters in review</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>geoTargeting</td>
  <td><a href="Location.md">Location</a></td>
  <td>Geographic Location</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>&lowast;Optional for Ad Customizer</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>advanced</td>
  <td>enum <a href="Advanced.md">Advanced</a></td>
  <td>Advcanced URL-compliant flag</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>&lowast;Optional for QuickLinks<br>&lowast;Default: TRUE</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="�N���G�C�e�B�u�E�R�����Y�E���C�Z���X" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />���� ��i �� <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">�N���G�C�e�B�u�E�R�����Y �\�� - ���ϋ֎~ 2.1 ���{ ���C�Z���X�̉��ɒ񋟂���Ă��܂��B</a>
