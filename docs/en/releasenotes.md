# Release Notes
Sponsored Search API ver.5.3

## Release version
5.3 (WSDL Version: 5.3.0)

## Types of Version update
Minor version up  
※Refer to the URL below for the type of version upgrade.
## Main contents of this release

#### 1. Added Site Retargeting function
Site retargeting function has been added. Details are listed below.<br>
・Each type of create, update, get function for target list are added. Type of target lists is as below:<br>
　-	Default list (Can issue the tag of retargeting)<br>
　-	Condition list<br>
　-	Combination list<br>
・Can target and/or exclude setting the target list to campaign or ad group<br>
 *Can only make exclude setting to campaign<br>
・Added retargeting to report type<br>
・Can retrieve operation history of target list<br>

* Target Web Service  
 * [RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)
 * [NegativeCampaignRetargetingListService](/docs/en/api_reference/services/NegativeCampaignRetargetingListService.md)
 * [AdGroupRetargetingListService](/docs/en/api_reference/services/AdGroupRetargetingListService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
 * [CutomerSyncService](/docs/en/api_reference/services/CutomerSyncService.md)

* Target Data Object  
 * Please confirm from the Entities document of each Services attached to the document folder.
  
* Target Enumerations  
 * Please confirm from the Enumerations document of each Services attached to the document folder.
  
#### 2. Added Mobile app download function
Mobile app download campaign function has been added. Details are listed below.<br>
・Can create campaign for Mobile app download.<br>
　・Added conversion tracking features for mobile app.<br>
　　- App first open conversion<br>
　　- In-app action conversion<br>
　・Added campaign type item in campaign report. Also, there will be a restriction in report creation as below:<br>
  　- Cannot create Destination URL report<br>
  　- Destination URL will return blank in Search query report.<br>
*Current campaign has renamed to “Standard campaign”.<br>
*Mobile app ads created from Standard campaign will not be displayed from mid-December 2015. Please move the ads that apply to this condition to Mobile app download campaign.
  
* Target Web Service
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md)
 * [AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md)

* Target Data Object  
 * Please confirm from the Entities document of each Services attached to the document folder.
  
* Target Enumerations  
 * Please confirm from the Enumerations document of each Services attached to the document folder.

#### 3. Added function upgrade
Partial function has been improved. Details are as follows.<br>
・Operation history for Data auto insertion has been added.<br>
・Can operate multiple ad groups in 1 request<br>
・Changed the maximum operation per request for several entities.<br>

* Target Web Service
 * [CustomerSyncService](/docs/en/api_reference/services/CustomerSyncService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)

* Target Data Object  
 * Please confirm from the Entities document of each Services attached to the document folder.
  
* Target Enumerations  
 * Please confirm from the Enumerations document of each Services attached to the document folder.

#### 4. Impact on each Version from the change of Services

<table class="standard">
<tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.5.2 or before</p>
</th>
<th valign="top">
  <p>Ver.5.3</p>
</th>
</tr>
<tr>
<td valign="top">
  <p>RetargetingListService</p>
</td>
<td valign="top">
  <p>- Not supported</p>
</td>
<td valign="top">
  <p>- New service
</td>
</tr>
<tr>
<td valign="top">
  <p>NegativeCampaign<br>RetargetingListService</p>
</td>
<td valign="top">
  <p>- Not supported</p>
</td>
<td valign="top">
  <p>- New service
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupRetargeting<br>ListService</p>
</td>
<td valign="top">
  <p>- Not supported</p>
</td>
<td valign="top">
  <p>- New service
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupService</p>
</td>
<td valign="top">
  <p>- Cannot select bidding strategy of conversion (TARGET_CPA、TARGET_ ROAS) for Mobile app campaign of iOS.<br>
  -Cannot get, update, delete the added field of target setting.</p>
</td>
<td valign="top">
  <p>- Added field to set target (settings) on ad group (AdGroup).<br>
- Added target type (Settings), target setting (TargetingSetting) entity.<br>
- Added criterion type (Criterion Type), narrow target setting (TargetAll).<br>
- Changed the maximum update and get operation.<br>
- Cannot select bidding strategy of conversion (TARGET_CPA、TARGET_ ROAS) for Mobile app campaign of iOS.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>ReportDefinitionService</p>
</td>
<td valign="top">
  <p>- Cannot set target list to report definition.<br>
- Cannot set target list to report type.</p>
</td>
<td valign="top">
  <p>- Added field to set target list ID (targetListIds) in report definition (ReportDefinition).<br>
- Added target list to report type (ReportType).</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CustomerSyncService</p>
</td>
<td valign="top">
  <p>- Cannot select target list and data auto insertion in entity type.<br>
- Cannot retrieve target list and data auto insertion.</p>
</td>
<td valign="top">
  <p>- Added retargeting (targetListId) and data auto insertion (feedFolderId) field for operation history (Auditlog).<br>
- Added target list and data auto insertion value to entity type (EntityType).</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignService</p>
</td>
<td valign="top">
  <p>- Cannot create Mobile app download.
*Cannot retrieve the item added in Ver.5.3.
- Cannot select bidding strategy of conversion (TARGET_CPA、TARGET_ ROAS) for Mobile app campaign of iOS.</p>
</td>
<td valign="top">
  <p>- Added item of Mobile app download campaign (campaignType, appStore, appId) to campaign (Campaign).<br>
- Added campaign type (Campaign Type) and app store type (App Store) type.<br>
- Changed the maximum update and get operation.<br>
- Cannot select bidding strategy of conversion (TARGET_CPA、TARGET_ ROAS) for Mobile app campaign of iOS.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupAdService</p>
</td>
<td valign="top">
  <p>- Cannot create mobile app download ads to standard campaign.<br>
- Cannot create text ads to Mobile app download campaign.</p>
</td>
<td valign="top">
  <p>- Cannot create mobile app download to standard campaign.<br>
- Cannot create text ads to Mobile app download campaign.<br>
- App store and app ID will automatically set for Mobile app download campaign.<br>
- For Android in mobile app campaign, setting of destination URL will be ignored.<br>
- Changed the maximum get operation.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>ConversionTrackerService</p>
</td>
<td valign="top">
  <p>- Setting of communication protocol (httpProtocol) in web conversion (webConversion) became unnecessary.</p>
</td>
<td valign="top">
  <p>- Setting of communication protocol (httpProtocol) in web conversion (webConversion) became unnecessary.<br>
- Added conversion info (snippetId. snippetLabel, appPostbackUrl) on app conversion tracker (AppConversion).<br>
- Added new app conversion function to app conversion type (AppConversionType).<br>
- Added flag of app post back URL (AppPostBackUrl)</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupCriterionService</p>
</td>
<td valign="top">
  <p>- For Android in mobile app campaign, setting of destination URL will be ignored.</p>
</td>
<td valign="top">
  <p>- For Android in mobile app campaign, setting of destination URL will be ignored.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>FeedItemService</p>
</td>
<td valign="top">
  <p>- Cannot connect to Data Auto Insertion for Mobile app download.<br>
*For Ver.5.2 only.</p>
</td>
<td valign="top">
  <p>- Cannot connect to Data Auto Insertion for Mobile app download.<br>
*There are no change in APIIF.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignFeedService</p>
</td>
<td valign="top">
  <p>- Cannot connect to Feed item for Mobile app download.</p>
</td>
<td valign="top">
  <p>- Cannot connect to Feed item for Mobile app download.<br>
*There are no change in APIIF.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupFeedService</p>
</td>
<td valign="top">
  <p>- NCannot connect to Feed item for Mobile app download.</p>
</td>
<td valign="top">
  <p>- Cannot connect to Feed item for Mobile app download.<br>
*There are no change in APIIF.</p>
</td>
</tr>
</tbody>
</table>

## Older Version Sunset Date  
Sponsored Search API Ver.5.0 will sunset in October 30, 2015(JST).  
Sponsored Search API Ver.5.1 is scheduled to sunset in March 2016 or later*.  
*We will inform once again, when the date is fixed.

