# Release Notes
Sponsored Search API V201901
## Release version
V201901 (WSDL Version: V201901)

## Main contents of this release
*For Target Data object and Enumuration, please confirm from data directory under API reference directory. 

### 1. Labels feature
The new 'Labels' feature enables to easily group and filter components such as campaigns and ads by setting up optional names to label them.
This has been released on the Campaign Management Tool in September 2018.<br>
Learn about details of this feature on the following help page.<br>
[What is Labels](https://support-marketing.yahoo.co.jp/promotionalads/ss/articledetail?lan=en&aid=17253)<br>
<br>
The following enhancements have been made on Sponsored Search API V201901:
1. Create/revise/remove labels
2. Set a label to campaign and other ad components

##### Target Web Service
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md)
 * [LabelService](/docs/en/api_reference/services/LabelService.md)
 * [CampaignLabelService](/docs/en/api_reference/services/CampaignLabelService.md)
 * [AdGroupLabelService](/docs/en/api_reference/services/AdGroupLabelService.md)
 * [AdGroupAdLabelService](/docs/en/api_reference/services/AdGroupAdLabelService.md)
 * [AdGroupCriterionLabelService](/docs/en/api_reference/services/AdGroupCriterionLabelService.md)  

### 2. Added Standard bidding and removed 'Maximize Conversions' option
Following two bidding settings are available after the new Auto Bidding feature 'Standard Bidding' has been released on December 2018.
* Standard bidding : The new bidding setting, which can be set on campaign level.
* Portfolio bidding : Existing bidding setting, which is created on account level and then set to multiple campaigns under the account. 
With this change, only "TRUE" is available as a value on CrossDeviceConversionFlag on creating/editing a conversion tracking.

Please check the following announcement to learn about change details.<br>
[New feature in Sponsored Search auto bidding released](https://biz.marketing.yahoo.co.jp/developercenter-en/announcement/616715/)<br>
<br>
Sponsored Search API V201901 mainly supports followings.
1. CampaignService supports setting of following auto bidding types as standard bidding<br>
‐ Maximize Clicks (TARGET_SPEND) <br>
‐ Target CPA (TARGET_CPA) <br>
‐ Target ROAS (TARGET_ROAS)
2. Removed 'Maximize Conversions' (ENHANCED_CPC) option as auto bidding type

##### Target Web Service
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md)

### 3. Added Custom Key of Site Retargeting
The Custom Key setting became available on Site Retargeting tag.<br>
Creating Target list using the custom key will enable Site Retargeting by accurate conditions.<br>
*The naming of this new feature has been revised from "Custom Parameter" to "Custom key".<br>
<br>
Sponsored Search API V201901 mainly supports followings.
1. The Custom Key setting became available on Site Retargeting tag.
2. Get Custom key setting information became available.

##### Remarks
The following behavior changes are planned on V201808 and before after V201901 release, on get/update conditions of Target List with one ore more condition(s) of 'Custom key' (Custom Parameter):
* Get all conditions set to Target List is unavailable.
* All of conditions previously set to the Target List are released and only new conditions are enabled.

Therefore you may have unexpected operation results when using 'Custom key' (Custom Parameter) on V201808 or before version.<br>
Please make sure and use the latest API version after V201901 release.
  
##### Target Web Service
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

### 4. Ad quality improvement
Sponsored Search will have activities for ad quality improvement by trademark restriction to protect brand value.<br>
<br>
The change on Sponsored Search API V201901 is following:
* Add a flag (TrademarkStatus) for trademark restriction and error codes.

*Validation error on ad creation including a restricted trademark (on all available versions).<br>
*We will announce additional information of this activity when available.

##### Target Web Service
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)

### 5. Auto-tagging feature is available
Auto-tagging feature supports conversion tracking tags available on secured browsers.<br>
<br>
Sponsored Search API V201901 mainly supports followings.
* Get/update setting informations of auto-tagging is available.

*This feature will be available for limited users.

##### Target Web Service 
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)

### 6. Maintenance Release
 * Removed some unnecessary items and reviewed some WSDL as system maintenance release.
 * As previously announced on the [announcement](https://biz.marketing.yahoo.co.jp/developercenter-en/announcement/574472/) on September 2018, revised responces of Auto Bidding setting on ad group level on Sponsored Search API. (on all available versions)

*See also the part of 'Impacts on each Version from the change of Services'. 

##### Target Web Service 
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [BidLandscapeService](/docs/ja/api_reference/services/BidLandscapeService.md)
 * [AccountTrackingUrlService](/docs/ja/api_reference/services/AccountTrackingUrlService.md)
 * [CampaignTargetService](/docs/ja/api_reference/services/CampaignTargetService.md)
 * [AdGroupWebpageService](/docs/ja/api_reference/services/AdGroupWebpageService.md)
 * [PageFeedItemService](/docs/ja/api_reference/services/PageFeedItemService.md)

## Impacts on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
V201808 and before</th>
<th>V201901</th>
</tr>
<tr>
 <td valign="top">CampaignService</td>
 <td valign="top">
 ・No change in API IF.<br>
 ・Following Auto Bidding types are referable<br>
 ‐ 'Maximize Clicks'(TARGET_SPEND)<br>
 ‐ 'Target CPA'(TARGET_CPA)<br>
 ‐ 'Target ROAS'(TARGET_ROAS)<br>
 </td>
 <td valign="top">
 ・Getting Label ID is available<br>
 ・Set/remove/get of following Auto Bidding types as Standard bidding are available<br>
 ‐ 'Maximize Clicks'(TARGET_SPEND)<br>
 ‐ 'Target CPA'(TARGET_CPA)<br>
 ‐ 'Target ROAS'(TARGET_ROAS)<br>
 ・Removed the related items of Auto Bidding type 'Maximize Conversions'(ENHANCED_CPC)<br>
 ・Removed Ad Rotation flag<br>
 ・Removed the related items of previous Auto Bidding (sunset on July, 2014)
 </td>
 </tr>
 <tr>
 <td valign="top">BiddingStrategyService</td>
 <td valign="top">
 No change in API IF.
 </td>
 <td valign="top">
 Removed the related items of Auto Bidding type 'Maximize Conversions' (ENHANCED_CPC)
 </td>
 </tr>
 <tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">
 ・No change in API IF.<br>
 ・Validation error on ad creation including a restricted trademark
 </td>
 <td valign="top">
 ・Validation error on ad creation including a restricted trademark<br>
 ・The value on flag is referable for confirming trademark restrictions
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupService</td>
 <td valign="top">
 ・No change in API IF.<br>
 ・Revised response on Auto Bidding setting on ad group<br>
 *Learn about details on <a href="https://biz.marketing.yahoo.co.jp/developercenter-en/announcement/574472/">announcement</a> on September 2018.
 </td>
 <td valign="top">
 ・Getting Label ID is available<br>
 ・Removed unnecessary items of Auto Bidding<br>
 ・Revised the response on Auto Bidding setting on ad group<br>
 *Learn about details on <a href="https://biz.marketing.yahoo.co.jp/developercenter-en/announcement/574472/">announcement</a> on September 2018.
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">
 ・No change in API IF. <br>
 ・Validation error on ad creation including a restricted trademark
 </td>
 <td valign="top">
 ・Getting Label ID is available<br>
 ・Validation error on ad creation including a restricted trademark<br>
 ・The value on flag is referable for confirming trademark restrictions
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupCriterionService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
 ・Getting Label ID is available<br>
 ・Removed unnecessary items of Auto Bidding
 </td>
 </tr>
 <tr>
 <td valign="top">LabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・Create, edit, remove, get labels is available
 </td>
 </tr>
 <tr>
 <td valign="top">CampaignLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・Set, release of campaign labels is available
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・Set, release of ad group labels is available
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupAdLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・Set, release of ad labels is available
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupCriterionLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・Set, release of keyword labels is available
 </td>
 </tr>
 <tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">
 No change in API IF. <br>
 ・On V201808 and before, changed the behavior on get/update conditions of Target List which with one ore more custome key (custom parameter) conditions as follows:<br>
 - Get all conditions set to the Target List is unavailable<br>
 - All of conditions previously set to the Target List are released and only new conditions are enabled
 </td>
 <td valign="top">
 ・Custom key is available as a condition of Target List<br>
 ・Get Custom key in the tag for Site Retargeting set to Advertiser's website is available
 </td>
 </tr>
 <tr>
 <td valign="top">BidLandscapeService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
 ・Added paging items to the selector of BidLandscapeService.wsdl
 </td>
 </tr>
 <tr>
 <td valign="top">AccountTrackingUrlService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
 ・Removed the operator enum value 'ADD' of AccountTrackingUrlService.wsdl (Because it's unprovided)
 </td>
 </tr>
 <tr>
 <td valign="top">ConversionTrackerService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
 ・Removed the flag to control Conversions across devices
 </td>
 </tr>
 <tr>
 <td valign="top">AccountService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
 ・Set/get Auto-tagging is available<br>
 *This feature will be available for limited users
 </td>
 </tr>
 <tr>
 <td valign="top">CampaignTargetService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
・Revised the response order of Page.Type and totalNumEntries of CampaignTargetService.wsdl like other services
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupWebpageService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
 ・Revised service name on AdGroupWebpageService.wsdl
 </td>
 </tr>
 <tr>
 <td valign="top">PageFeedItemService</td>
 <td valign="top">
 ・No change in API IF.
 </td>
 <td valign="top">
 ・Revised service name on AdGroupWebpageService.wsdl<br>
 ・Revised the value on maxOccurs of operations from "unbounded" to "1" on AdGroupWebpageService.wsdl
 </td>
 </tr>
 </tbody>
</table>

## Sunset schedule of Sponsored Search API V201805
Sponsored Search API V201805 is scheduled to sunset as follows.  
* Deprecation Date (Support closing on) : February 28, 2019.<br>
* End of Life Date (System closing on)  : May 29, 2019.<br>
