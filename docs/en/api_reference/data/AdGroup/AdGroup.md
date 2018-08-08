# AdGroup
AdGroup object describes ad group information.

### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

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
  <td>Account ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>campaignTrackId</td>
  <td>xsd:long</td>
  <td>Campaign ID for tracking.<br>* "0" will return in Sandbox.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>Campaign name.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>Ad Group ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>adGroupTrackId</td>
  <td>xsd:long</td>
  <td>Ad Group ID for tracking.<br>* "0" will return in Sandbox.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>Ad Group name.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>Ad display status from user's settings.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyConfiguration</td>
  <td><a href="AdGroupBiddingStrategy.md">AdGroupBiddingStrategy</a></td>
 <td>Bidding setting which is currently available.<br>*After November 15, 2017 JST, creating/editing bidding setting is not available.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
<tr>
<td>biddingStrategyFailedReason</td>
<td>enum <a href="BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a></td>
<td>Reason of failed Auto Bidding setting.<br>*This field shows when setting has actually failed.</td>
<td>yes</td>
<td>Ignore</td>
<td>Ignore</td>
<td>Ignore</td>
</tr>
<tr>
<td>failedBiddingStrategyConfiguration</td>
<td><a href="AdGroupBiddingStrategy.md">AdGroupBiddingStrategy</a></td>
<td>Settings in detail on the failed Auto Bidding creation.<br>*This field shows when setting has actually failed.</td>
<td>yes</td>
<td>Ignore</td>
<td>Ignore</td>
<td>Ignore</td>
</tr>
<tr>
  <td>settings[0...1]</td>
  <td><a href="AdGroupSettings.md">AdGroupSettings</a><br>inherited <a href="TargetingSetting.md">TargetingSetting</a></td>
  <td>Targeting setting.</td>
  <td>yes</td>
  <td>Optional<br>
  *Default value for the case of no setting 'TargetingSetting'<br>
  TargetCriterionType:TARGET_LIST<br>
  TargetAll:ACTIVE</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL.<br>* Cannot set for a Mobile App campaign for Android OS.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>* Cannot update when this is in editorial review.<br>*Not to be reviewed if there is no change.</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>Custom parameter.<br>* Cannot set for a Mobile App campaign for Android OS.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>* Cannot update this when Tracking URL is in editorial review.<br>*Not to be reviewed if there is no change.</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>urlReviewData</td>
  <td><a href="UrlReviewData.md">UrlReviewData</a></td>
  <td>Editorial review status of URL.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupAdRotationMode</td>
  <td><a href="AdGroupAdRotationMode.md">AdGroupAdRotationMode</a></td>
  <td>Ad rotation setting for optimizing.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
