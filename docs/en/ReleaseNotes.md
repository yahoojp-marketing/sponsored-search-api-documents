# Release Note
Sponsored Search API Ver.6.3<br>

## Release version
6.3 (WSDL version : 6.3.0)

## Type of version up
Minor version up  

## Main features enhancement on the release
*Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations).
<br><br>

#### 1. Function improvement on "Site Retargeting"
 * This feature enables the target list to be shared across accounts under the same advertiser. It supports to create and edit Target List to be shared between accounts. 
 * “Include” option can be available for setup Target List to campaign, adding to the “Exclude” option which is currently used.<br><br>

##### Target Web Service 
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)
 * [CampaignRetargetingListService](/docs/ja/api_reference/services/CampaignRetargetingListService.md)
 * NegativeCampaignRetargetingListService (End support)
<br><br>

#### 2.	Additional upgrades
Following web services have been updated.<br>
More change details of each service are referable on the matrix of 'Impact on each version from the change of services' below.
<br>
<br>

##### Target Web Service
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)
 * [AdGroupRetargetingListService](/docs/ja/api_reference/services/AdGroupRetargetingListService.md)
<br><br>


## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.6.2 or before</p>
</th>
<th valign="top">
  <p>Ver.6.3</p>
</th>
</tr>
<tr>
  <td colspan="3"><b>1. Site Retargeting feature enhancemenmt</b></td>
</tr>
<tr>
 <td valign="top">CampaignService</td>
 <td valign="top">No change.</td>
 <td valign="top">
 ・Set/browse Target user of Site Retargeting (targetAll) are available.
 </td>
</tr>
<tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">No change.<br>
 ・Add/edit/browse excluded Target list are available.<br>
 ・Browse excluded Site retargeting tag is available.<br>
 </td>
 <td valign="top">Following Site retargeting feature improvement.<br>
 ・Add/edit/browse Target list (both excluded and shared list) are available.<br>
 ・Browse Site retargeting tag (both excluded and shared list) is available.<br>
 ・Target list ID for tracking (targetListTrackId) is available.<br>
 ・Added error codes.
 </td>
</tr>
<tr>
 <td valign="top">NegativeCampaignRetargetingListService</td>
 <td valign="top">Available.</td>
 <td valign="top">Not supported.<br>※The function is replaced with CampaignRetargetingListService.</td>
</tr>
<tr>
 <td valign="top">CampaignRetargetingListService</td>
 <td valign="top">Not supported.</td>
 <td valign="top">Available (New service).<br>
 ・The "Include" option is available when setting Target list for campaigns.<br>
 ・The "Exclude" option is available when setting Target List for campaigns.<br>
 ・Added error codes.
 </td>
</tr>
<tr>
  <td colspan="3"><b>2.	Additional upgrades</b></td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">No change.</td>
 <td valign="top">・It browses the information which can be specified or cannot be specified on "getReportFields".<br>
 ・It browses report fields which cannot be specified together.
 </td>
</tr>
<tr>
 <td valign="top">ReportService</td>
 <td valign="top">No change.</td>
 <td valign="top">"get" can browse "reportName" (which can be specified by ReportDefintionService/add).</td>
</tr>
<tr>
 <td valign="top">AccountService</td>
 <td valign="top">No change.</td>
 <td valign="top">New option "CANCELED" is available on AccountStatus.<br>It enables to browse cancelled account.</td>
</tr>
<tr>
 <td valign="top">AdGroupRetargetingListService</td>
 <td valign="top">No change.</td>
 <td valign="top">Added error codes.<br>No specification change.</td>
</tr>
</table>

