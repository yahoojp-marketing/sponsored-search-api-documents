# Release Notes
Sponsored Search API V201808
## Release version
V201808 (WSDL Version: V201808)

## Main contents of this release
*For Target Data object and Enumuration, please confirm from data directory under API reference directory. 

### 1. Dynamic Ads for Search
With Dynamic Ads for Search, you can automatically generate and show your ad title to a keyword highly relevant to the website content you specified. 
The following enhancements have been made on Sponsored Search API:

1. Creating ads of Dynamic Ads for Search and Page Feed feature have been added.
2. Report types below for Dynamic Ads for Search have been added.<br>
‐Search Query report (Dynamic Ads for Search)<br>
‐Page Feed Targeting Report<br>
*[List of Sponsored Search API report fields](/docs/en/api_reference/appendix/reportfields.md) are also available.

##### Target Web Service
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [FeedFolderService](/docs/en/api_reference/services/FeedFolderService.md)
 * [PageFeedItemService](/docs/en/api_reference/services/PageFeedItemService.md)
 * [CampaignWebpageService](/docs/en/api_reference/services/CampaignWebpageService.md)
 * [AdGroupWebpageService](/docs/en/api_reference/services/AdGroupWebpageService.md)
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/en/api_reference/services/ReportService.md)

### 2. Change on values of Conversion tracking across different devices
There was a change on the option CrossDeviceConversionFlag (a flag to control conversion tracking across different device on/off) in ConversionTrackerService.<br>
With this change, only "TRUE" is available as a value on CrossDeviceConversionFlag on creating/editing a conversion tracking.

* Create new (ADD)
  * If no value has been set on CrossDeviceConversionFlag<br>
  The default “TRUE” is set as its value and it responds the "TRUE".
  * If any value has been set on CrossDeviceConversionFlag<br>
  The set value is processed as Ignore and it responds the value "TRUE".
* Update (SET)
  * If any value has been set on CrossDeviceConversionFlag<br>
  The set value is processed as Ignore and it responds the value "TRUE" regardless of the value set on.

**These changes have been applied to the lower versions (Ver.6.5.0/V201805) similarily.

##### Target Web Service
 * [ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md)

### 3. New Auto Bidding type which replaces 'Maximize Conversions'
For ENHANCED_CPC (maximize conversions) on Auto Bidding feature, following changes are planned.

* ENHANCED_CPC sunset
* Release of new Auto Bidding type switched from ENHANCED_CPC

According to this change, a new interface to provide a new Auto Bidding type will be provided on V201808.
Learn more details on 'Impact on each Version from the change of Service' 

##### Remarks
* It's just providing a new interface.  Creating a new setting with Auto Bidding type is not available yet as of V201808 release date.
* We will inform the closing of ENHANCED_CPC and details of new Auto Bidding type when it's fixed.
* ENHANCED_CPC will be continuously available after V201808 release.
  
##### Target Web Service
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)

### 4. Maximum length of duration of Reach Status of Site Retargeting enhanced
Maximum length of available duration for Target List (Duration of Reach Status for pages using Site Retargeting tag）has been revised as follows.<br>
(Before) 180days -> (After) 540days

**No change on the default duration 180 days.<br>
**These changes have been applied to the lower versions (Ver.6.5.0/V201805) similarily.

##### Target Web Service
 * [RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)

### 5. Maintenance Release
Some of Web Services will have maintenance release. 

* Some error codes have been reexamined its configuration and reorganized.<br>
Details are available on '[Error codes reorganization](/docs/en/api_reference/appendix/error_codes_structure.md)'
* Improved the accuracy of Keyword Suggestion feature.<br>
With this update, a new search criteria 'accountId' has been added as a required item for TargetingIdeaService.<br>
<br>
* See also the part of 'Impacts on each Version from the change of Services'.

##### Target Web Service 
 * All services (error codes changes)
 * [TargetingIdeaService](/docs/en/api_reference/services/TargetingIdeaService.md)

## Impacts on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
V201805 or before
</th>
<th>
V201808
</th>
</tr>
<tr>
 <td valign="top">CampaignService</td>
 <td valign="top">No change in API IF.<br>
  **DYNAMIC_ADS_FOR_SEARCH (Dynamic Ads for Search) provides deleting operation only.<br>
  **There is no change on Bidding setting.
 </td>
 <td valign="top">
  ・Following operations are now available on DYNAMIC_ADS_FOR_SEARCH (Dynamic Ads for Search).<br>
  　‐get<br>
  　‐add<br>
  　‐update<br>
  　‐remove<br>
  ・There are following changes on Bidding setting.<br>
  　‐To set a new Auto Bidding type which replaces 'Maximize Conversions' (will be available after the new auto bidding type release)<br>
    Set 'MANUAL_CPC' for biddingStrategyType (bidding type) AND set 'TRUE' for enhancedCpcEnabled.<br>
  　‐To set Manual Bidding<br>
  　Set 'MANUAL_CPC' for biddingStrategyType (bidding type) AND set nothing or set 'FALSE' for enhancedCpcEnabled.<br><br>
  **When requesting with no setting on biddingScheme option, enhancedCpcEnabled will respond 'FALSE'.<br>
  **Currently available ENHANCED_CPC (Maximize Conversions) will be supported for a while after the new type released.
</td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">No change in API IF.<br>
  **DYNAMIC_ADS_FOR_SEARCH (Dynamic Ads for Search) provides deleting operation only.
 </td>
 <td valign="top">
  ・DYNAMIC_SEARCH_LINKED_AD (Dynamic Ads for Search) has been added as a new AdType (ad type).<br>
  ・Following operations are now available on DYNAMIC_ADS_FOR_SEARCH (Dynamic Ads for Search).<br>
  　‐get<br>
  　‐add<br>
  　‐update<br>
  　‐remove<br>
  ・Information of Dynamic Ads for Search has been added to creative information.
 </td>
</tr>
<tr>
 <td valign="top">FeedFolderService</td>
 <td valign="top">No change in API IF.<br>
  **DYNAMIC_ADS_FOR_SEARCH (Dynamic Ads for Search) provides deleting operation only.
 <td valign="top">
  ・DYNAMIC_SEARCH_LINKED_AD (Dynamic Ads for Search) has been added as a new AdType (ad type).<br>
  ・Information of Dynamic Ads for Search has been added to creative information.
</td>
</tr>
<tr>
 <td valign="top">PageFeedItemService</td>
 <td valign="top">Not supported.</td>
 <td valign="top">
  Following operations are now available for Page Feed item.<br>
  　-upload<br>
  　-download<br>
  　-get summary information<br>
</td>
</tr>
<tr>
 <td valign="top">CampaignWebpageService</td>
 <td valign="top">Not supported.</td>
 <td valign="top">
  Following operations are now available for Page Feed Exclude settings on a campaign level.<br>
  　-get<br>
  　-add<br>
  　-remove
</td>
</tr>
<tr>
 <td valign="top">AdGroupWebpageService</td>
 <td valign="top">Not supported.</td>
 <td valign="top">
  Following operations are now available for Page Feed Allow/Exclude settings on an ad group level.<br>
  　-get<br>
  　-add<br>
  　-update<br>
  　-remove
</td>
</tr>
<tr>
 <td valign="top">ConversionTrackerService</td>
 <td valign="top">No change in API IF.<br>
 <td valign="top">
  There were some changes on behavior of setting CrossDeviceConversionFlag (Control flag of Cross Device Conversion tracking).<br>
  　‐Creating new (ADD)<br>
  　Responds the value 'TRUE', regardless of the setting status.<br>
  　‐Editing (SET)<br>
  　When any value has been set, responds the value 'TRUE' (ignores any setting value).
</td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">No change in API IF.<br>
  **Add/Update/Remove of reporting types related to Dynamic Ads for Search are not available.
 <td valign="top">
  Following reporting types have been added.<br>
  　‐KEYWORDLESS_QUERY (Search Query Report (Dynamic Ads for Search)）<br>
  　‐WEBPAGE_CRITERION (Page Feed Targeting Report)
</td>
</tr>
<tr>
 <td valign="top">ReportService</td>
 <td valign="top">No change in API IF.<br>
  **Add/Update/Remove of reporting types related to Dynamic Ads for Search are not available.
 <td valign="top">
  Following reporting types have been added.<br>
  　‐KEYWORDLESS_QUERY (Search Query Report (Dynamic Ads for Search)）<br>
  　‐WEBPAGE_CRITERION (Page Feed Targeting Report)
</td>
</tr>
<tr>
 <td valign="top">TargetingIdeaService</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">Added accountId as a required option for search condition.</td>
</tr>
<tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">No change in API IF.<br>
 **Enhanced the maximum length of reachStorageSpan from 180 days to 540 days.<br>
  **Default value is 180 days.</td>
 <td valign="top">No change in API IF.<br>
 **Enhanced the maximum length of reachStorageSpan from 180 days to 540 days.<br>
  **Default value is 180 days.</td>
</tr>
<tr>
 <td valign="top">All services</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">Some error codes have been reexamined its confifuration and reorganized</td>
</tr>
</table>

## Sunset schedule of Sponsored Search API Ver.6.5
Sponsored Search API Ver.6.5 is scheduled to sunset as follows.  
* Deprecation Date (Support closing on) : September 10, 2018.<br>
* End of Life Date (System closing on)  : December 10, 2018.<br>
