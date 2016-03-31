# BiddableAdGroupCriterion
BiddableAdGroupCriterion object displays biddable criterion in ad group.

### ServiceInheritance
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
  <td colspan="8"><a href="./AdGroupCriterion.md">AdGroupCriterion</a>(inherited)</td>
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
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>campaignTrackId</td>
  <td>xsd:long</td>
  <td>Campaign ID for tracking.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>Campaign name.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>Ad group ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>adGroupTrackId</td>
  <td>xsd:long</td>
  <td>Ad group ID for tracking.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>Ad group name.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>criterionUse</td>
  <td>enum <a href="./CriterionUse.md">CriterionUse</a></td>
  <td>Criterion type.<br>It can select to set as bid or negative keyword.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>criterion</td>
  <td><a href="./Criterion_AdGroupCriterion.md">Criterion</a><br>inherited <a href="./Keyword_AdGroupCriterion.md">Keyword</a></td>
  <td>Criteria of Ad group.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td colspan="8">BiddableAdGroupCriterion</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>Status of ad that been set.<br>* If there is no designation, all ads in all condition will return./td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatus</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Editorial review status.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes</td>
  <td>xsd:string</td>
  <td>Code of Disapproval reason.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>destinationUrl</td>
  <td>xsd:string</td>
  <td>Custom URL of before upgrading.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>reviewDestinationUrl</td>
  <td>xsd:string</td>
  <td>Custom URL of before upgrading, in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>biddingStrategyConfiguration</td>
  <td><a href="./BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a></td>
  <td>Bid setting.<br>* Currently available bid setting will respond.<br>* Apply the bid setting that is available on parent entity.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>biddingStrategyFailedReason</td>
  <td>enum <a href="../data/BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a></td>
  <td>Reason that Auto bidding has failed.<br>* It will respond only when failed.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>failedBiddingStrategyConfiguration</td>
  <td><a href="./BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a></td>
  <td>Auto bidding that failed to register.<br>* It will respond only when failed.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <td>advancedUrl</td>
  <td>xsd:string</td>
  <td>Upgraded Custom URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>* Require- ment when designating tracking URL after the upgrade.<br>* Ignore when not updating (advanced =FALSE).</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewAdvancedUrl</td>
  <td>xsd:string</td>
  <td>Upgraded Custom URL, in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <td>advancedMobileUrl</td>
  <td>xsd:string</td>
  <td>Upgraded Custom URL (Smartphone).</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>* Ignore when not updating (advanced =FALSE).</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewAdvancedMobileUrl</td>
  <td>xsd:string</td>
  <td>Upgraded Custom URL (Smartphone), in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewTrackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL, in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>Custom paramters.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>* Ignore when not updating (advanced =FALSE).</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewCustomParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>Custom paramters, in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <td>advanced</td>
  <td>enum <a href="./Advanced.md">Advanced</a></td>
  <td>Flag of Advanced URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
