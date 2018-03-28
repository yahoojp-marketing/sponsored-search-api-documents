# Campaign
Campaign object describes Campaign information.

### Service
+ [CampaignService](../services/CampaignService.md)

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
  <td>Ignore</td>
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
  <td>Campaign name.<br>* Insert limit: Up to 50 characters.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatuses</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>Status of ad display set by user.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>servingStatus</td>
  <td>enum <a href="./CampaignServingStatus.md">CampaignServingStatus</a></td>
  <td>Display status in Campaign level.<br>Return the campgin status regardless of display status set from user (userStatuses).</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>Start date of Campaign.<br>*Cannot set the past date.<br>*Cannot change the date to the campaign that is already active.</td>
  <td>yes</td>
  <td>Optional<br>*Default: Current date.</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>End date of Campaign.<br>*Cannot set the past date and date before the start date.</td>
  <td>yes</td>
  <td>Optional<br>※Default: 20371231</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>budget</td>
  <td><a href="./Budget.md">Budget</a></td>
  <td>Campaign budget.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyConfiguration</td>
  <td><a href="./CampaignBiddingStrategy.md">CampaignBiddingStrategy</a></td>
  <td>Bid setting.<br>*BudgetOptimizer is not available.<br>*If iOS is selected for App Campaign, cannot set "TARGET_CPA" or "TARGET_ROAS".</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>biddingStrategyFailedReason</td>
  <td>enum <a href="./BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a></td>
  <td>Reason of Auto Bidding set has failed.<br>*This field shows when setting has actually failed.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>failedBiddingStrategyConfiguration</td>
  <td><a href="./CampaignBiddingStrategy.md">CampaignBiddingStrategy</a></td>
  <td>Reason of Auto Bidding creation has failed.<br>*This field shows when setting has actually failed.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionOptimizerEligibility</td>
  <td>enum <a href="./ConversionOptimizerEligibility.md">ConversionOptimizerEligibility</a></td>
  <td>Determines if eligible to use Conversion Optimizer.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adServingOptimizationStatus</td>
  <td>enum <a href="./AdServingOptimizationStatus.md">AdServingOptimizationStatus</a></td>
  <td>Setting of Ad rotation for optimizing ad display.<br>*This item of 'Ad rotation' on campaign level has been changed to read-only.</td>
  <td>yes</td>
  <td>Ignore<br>*Default: OPTIMIZE is set.<br>It's not editable with other value.</td>
  <td>Ignore<br>*The value which has been already set for this item is responded.<br>It's not editable with other value.</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>settings[0..2]</td>
  <td>
  <a href="./CampaignSettings.md">CampaignSettings</a><br>
  inherited <a href="./GeoTargetTypeSetting.md">GeoTargetTypeSetting</a><br>
  inherited <a href="./TargetingSetting.md">TargetingSetting</a>
  </td>
  <td>Setting of target and matching.</td>
  <td>yes</td>
  <td>Optional<br>
  *Default value for the case of no setting 'TargetingSetting'<br>
  SettingType:TARGET_LIST_SETTING<br>
  TargetAll:ACTIVE</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignType</td>
  <td>enum <a href="./CampaignType.md">CampaignType</a></td>
  <td>Campaign type.</td>
  <td>yes</td>
  <td>Optional<br>※Default: STANDARD</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appStore</td>
  <td>enum <a href="./AppStore_Campaign.md">AppStore</a></td>
  <td>Selection of App store.</td>
  <td>yes</td>
  <td>If campaignType is 'STANDARD':ignore<br>
   If campaignType is 'MOBILE_APP':Requirement<br>
   If campaignType is 'DYNAMIC_ADS_FOR_SEARCH_SETTING':ignore
  </td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appId</td>
  <td>xsd:string</td>
  <td>App ID (for iOS) or Package name (for Android).<br>*Input only the numbers for iOS in Mobile App Campaign.</td>
  <td>yes</td>
  <td>If campaignType is 'STANDARD':ignore<br>
   If campaignType is 'MOBILE_APP':Requirement<br>
   If campaignType is 'DYNAMIC_ADS_FOR_SEARCH_SETTING':ignore
  </td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL.<br>*Cannot set if Mobile App Campaign is in Android.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>*Cannot update during review.<br>*If there is no change on this field, it will not be reviewed.</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>Custom Parameter.<br>*Cannot set if Mobile App Campaign is in Android.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>*Cannot update when Tracking URL is in review.<br>*If there is no change on this field, it will not be reviewed.</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>urlReviewData</td>
  <td><a href="./UrlReviewData.md">UrlReviewData</a></td>
  <td>Review status of URL.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
