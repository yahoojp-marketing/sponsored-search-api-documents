# BiddableAdGroupCriterion
BiddableAdGroupCriterion object displays biddable criterion in ad group.

### ServiceInheritance
+ [AdGroupCriterionService](../../services/AdGroupCriterionService.md)

### Namespace
[AdGroupCriterionService#Namespace](../../services/AdGroupCriterionService.md#namespace)

### Inheritance
+ [AdGroupCriterion](AdGroupCriterion.md)

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
  <td colspan="8"><a href="AdGroupCriterion.md">AdGroupCriterion</a>(inherited)</td>
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
  <td>enum <a href="AdGroupCriterionUse.md">AdGroupCriterionUse</a></td>
  <td>Criterion type.<br>It can select to set as bid or negative keyword.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>criterion</td>
  <td><a href="Criterion.md">Criterion</a><br>inherited <a href="Keyword.md">Keyword</a></td>
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
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>Ad distribution status which is set by user.<br>* If there is no designation, all ad distribution statuses are included in filtering condition.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatus</td>
  <td>enum <a href="ApprovalStatus.md">ApprovalStatus</a></td>
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
  <td>Custom URL of before upgrading.<br>*When tag is set blank, existing Custom URL before upgrade will be deleted.</td>
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
  <td>bid</td>
  <td><a href="Bid.md">Bid</a></td>
  <td>Bid values.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <td>advancedUrl</td>
  <td>xsd:string</td>
  <td>Upgraded Custom URL.<br>*When this is set blank, existing upgraded Custom URL will be deleted.</td>
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
 <tr>
  <td>additionalAdvancedUrls</td>
  <td><a href="AdGroupCriterionAdditionalAdvancedUrls.md">AdGroupCriterionAdditionalAdvancedUrls</a></td>
  <td>Additional setting of Landing Page URL.<br>Setting of 'advancedUrl' is required to make this additional setting.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <td>advancedMobileUrl</td>
  <td>xsd:string</td>
  <td>Upgraded Custom URL (Smartphone).<br>*When tag is set blank, existing upgraded Custom URL (Smartphone) will be deleted.</td>
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
 <tr>
  <td>additionalAdvancedMobileUrls</td>
  <td><a href="AdGroupCriterionAdditionalAdvancedMobileUrls.md">AdGroupCriterionAdditionalAdvancedMobileUrls</a></td>
  <td>Additional setting of Smartphone Landing Page URL. <br>Setting of 'AdvancedMobileUrls' is required for this additional setting.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
 <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL.<br>*When tag is set blank, existing Tracking URL will be deleted.</td>
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
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>Custom paramters.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>* Ignore when not to be updated (advanced =FALSE).</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewCustomParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>Custom paramters, in review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
