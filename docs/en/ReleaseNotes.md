# Release Notes
Sponsored Search API Ver.6.0

## Release version
6.0 (WSDL Version: 6.0.0)

## Types of Version update
Major version up

## Main contents of this release

#### 1. Sponsored Search system enhancement "Advanced URL"
To improve the operation of Destination URL and Custom URL, we will release Sponsored Search system enhancement “Advanced URL”. Details are as follows.<br>

##### URL Settings
* Tracking URL setting will be avaialble for services below.*<br>
　・AccountTrackingUrlService<br>
　・CampaignService<br>
　・AdGroupService<br>
　・AdGroupAdService<br>
　・AdGroupCriterionService<br>
　・FeedItemService<br>
 *Tracking URL will go on review, so retieving the elements below will be possible:<br>
　 - Review status<br>
　 - Code of disapproval reason<br>
　 - In review and/or disapproved Tracking URL <br>
* Retrieving the Tracking ID below will be available.<br>
　・CampaignID<br>
　・AdGroupID<br>
　・AdGroupCriterionID<br>
　・FeedItemID<br>
　・RetargetingListID<br>
* Setting of Custom Parameters will be available for services below.<br>
　・CampaignService<br>
　・AdGroupAdService<br>
　・AdGroupCriterionService<br>
　・AdGroupService<br>
　・FeedItemService<br>
* Destination URL will become Landing Page URL for services below.*<br>
　・AdGroupAdService<br>
　・AdGroupCriterionService<br>
　・FeedItemService<br>
 *During the upgrade period, update of current Destination URL (before the upgrade to Landing Page URL) is possible.<br>
* Tracking parameter below will be available.<br>
　・lpurl: Can obtain Landing Page URL. Available for Tracking URL only. 

##### Upgrade in report
* Landing Page URL Report will be created.<br>
* Destination URL Report will be deleted (January 13th, 2016 (Wed) JST).<br>
* "Landing Page URL" will be added as new report field for reports below.<br>
　・Ad Report<br>
　・Keyword Report<br>
　・Ad Display Option Report<br>
* "Tracking URL" and "Custom Parameter" will be added as new report field for report below.<br>
　・Account Report* <br>
　・Campaign Report<br>
　・Ad Group Report<br>
　・Ad Report<br>
　・Keyword Report<br>
　・Ad Display Option Report<br>
　*Only "Tracking URL" field will be added.<br>

##### Others
* Calculation method of character/word will change.<br>
　Below objectives will be reflected.<br>
　・Ad<br>
　　・Headline<br>
　　・Description<br>
　　・Description 2<br>
　　・Display URL<br>
　・FeedItem<br>
　　・Link text<br>
* URL setting will change.<br>
　・Japanese word domain will be available to use.<br>
　・All Top Level Domain (TLD) will be available to use.<br>
　*All domain will go to review.<br>
* BulkService will end support.
<br><br>

##### Target Web Service 
 * [AccountTrackingUrlService](/docs/en/api_reference/services/AccountTrackingUrlService.md)
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/en/api_reference/services/ReportService.md)
 * [RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)
 * BulkService (End support)
<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

#### 2. Enhancement of Report Functions
Additonal and change in report functions. Details are as follows.<br>
* Report segment will be determined automatically and created from the combination of Report field.<br>
 *This function will not be available for older versions. (Ver.5.X)<br>
* Code designated from filter will designate the item to display report.<br>
* Download URL retrieval (getDownloadUrl of ReportService) operation of report will end support.<br>
 *From this version, Download URL can be retrieved from get operation of ReportService.<br>
* Type of "Total Conversions" field will change from long to double.
<br><br>

##### Target Web Service 
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/en/api_reference/services/ReportService.md)
<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

#### 3. Addional upgrades
Partial function has been improved. Details are as follows.<br>
* Negative keyword setting function from keyword suggestion service will end support.<br>
* Export function will be available.<br>
　Can collectively obtain the campaign, ad group, keyword, and ad information.<br>
　*Schedued to release after April 13th (JST).
<br><br>

##### Target Web Service
 * [TargetingIdeaService](/docs/en/api_reference/services/TargetingIdeaService.md)
 * [CampaignExportService](/docs/en/api_reference/services/CampaignExportService.md)
<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.

## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.5.3 or before</p>
</th>
<th valign="top">
  <p>Ver.6.0</p>
</th>
</tr>
<tr>
 <td colspan="3"><b>Sponsored Search system enhancement "Advanced URL"</b></td>
</tr>
<tr>
<td valign="top">
  <p>AccountTrackingUrlService</p>
</td>
<td valign="top">
  <p>- Not supported.</p>
</td>
<td valign="top">
  <p>- New service.</p>
</td>
</tr>
 <tr>
 <td valign="top">
  <p>AdGroupAdService</p>
</td>
<td valign="top">
  <p>- Following cannot get/add/set/remove.<br>
　・Landing Page URL<br>
　・Landing Page URL (Smartphone)<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Ad cannot be retrieved after Advanced URL upgrade.<br>
- Calculation method of character/word will change (for Ver.5.2, Ver.5.3 only).<br>
- URL setting will change (for Ver.5.2, Ver.5.3 only).</p>
</td>
<td valign="top">
  <p>- Following can get/add/set/remove.<br>
　・Landing Page URL<br>
　・Landing Page URL (Smartphone)<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Calculation method of character/word will change.<br>
- URL setting will change.</p>
</td>
</tr>
 <tr>
 <td valign="top">
  <p>AdGroupCriterionService</p>
</td>
<td valign="top">
  <p>- Following cannot get/add/set/remove.<br>
　・Landing Page URL<br>
　・Landing Page URL (Smartphone)<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Cannot retrieve Tracking ID.<br>
- Keyword cannot be retrieved after Advanced URL upgrade.<br>
- URL setting will change (for Ver.5.2, Ver.5.3 only).</p>
</td>
<td valign="top">
  <p>- Following can get/add/set/remove.<br>
　・Landing Page URL<br>
　・Landing Page URL (Smartphone)<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Can retrieve Tracking ID.<br>
- URL setting will change.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupService</p>
</td>
<td valign="top">
  <p>- Following cannot get/add/set/remove.<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Cannot retrieve Tracking ID.
- Ad group cannot be retrieved after Advanced URL upgrade.</p>
</td>
<td valign="top">
  <p>- Following can get/add/set/remove.<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Can retrieve Tracking ID.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>BulkService</p>
</td>
<td valign="top">
  <p>- No change.</p>
</td>
<td valign="top">
  <p>- Service will end support.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignService</p>
</td>
<td valign="top">
  <p>- Following cannot get/add/set/remove.<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Cannot retrieve Tracking ID.<br>
- Campaign cannot be retrieved after Advanced URL upgrade.</p>
</td>
<td valign="top">
  <p>- Following can get/add/set/remove.<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Can retrieve Tracking ID.<br>
- Similar keyword matching will end support.<br>
</td>
</tr>
<tr>
<td valign="top">
  <p>FeedItemService</p>
</td>
<td valign="top">
  <p>- Following cannot get/add/set/remove.<br>
　・Landing Page URL<br>
　・Landing Page URL (Smartphone)<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Cannot retrieve Tracking ID.<br>
- Feed item cannot be retrieved after Advanced URL upgrade.<br>
- Calculation method of character/word will change (for Ver.5.2, Ver.5.3 only).<br>
- URL setting will change (for Ver.5.2, Ver.5.3 only).</p>
</td>
<td valign="top">
  <p>- Following can get/add/set/remove.<br>
　・Landing Page URL<br>
　・Landing Page URL (Smartphone)<br>
　・Tracking URL<br>
　・Custom Parameter<br>
- Can retrieve Tracking ID.<br>
- Calculation method of character/word will change.<br>
- URL setting will change.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>RetargetingListService</p>
</td>
<td valign="top">
  <p>- Cannot retrieve Tracking ID.</p>
</td>
<td valign="top">
  <p>- Can retrieve Tracking ID.</p>
</td>
</tr>
<tr>
 <td colspan="3"><b>Enhancement of Report Functions</b></td>
</tr>
<tr>
<td valign="top">
  <p>ReportDefinitionService</p>
</td>
<td valign="top">
  <p>- No change.<br>
- Destination URL will be deleted.</p>
</td>
<td valign="top">
  <p>- set operation will end support.<br>
- Segment selection will end support.<br>
- New report type will be added.<br>
- New report field will be added to several current report type.<br>
- Destination URL Report will end support.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>ReportService</p>
</td>
<td valign="top">
  <p>- No change.</p>
</td>
<td valign="top">
  <p>- getDownloadUrl operation will end support.*<br>
  *Download URL retrieval will be available from get operation.</p>
</td>
</tr>
<tr>
 <td colspan="3"><b>Addional upgrades</b></td>
</tr>
<tr>
<td valign="top">
  <p>TargetingIdeaService</p>
</td>
<td valign="top">
  <p>- No change.</p>
</td>
<td valign="top">
  <p>- Setting of Negative keyword (ExcludedKeywordSearchParameter) will be deleted.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignExportService</p>
</td>
<td valign="top">
  <p>- Not supported.</p>
</td>
<td valign="top">
  <p>- New service.</p>
</td>
</tr>
</tbody>
</table>

## Sunset Date of Older Version of Sponsored Search API
* Following versions will end support after the Advanced URL upgrade period (October 2016 or later).<br>
・Sponsored Search API Ver.5.1<br>
・Sponsored Search API Ver.5.2<br>
・Sponsored Search API Ver.5.3<br>
<br>
