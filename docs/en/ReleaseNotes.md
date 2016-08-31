# Release Note
Sponsored Search API Ver.6.1<br>

## Release version
6.1(WSDL version : 6.1.0)

## Type of version up
Minor version up  

## Main features enhancement on the release

#### 1. Add "Negative Keyword List" sharing function
Negative keywords can be managed by single list which is shared with each component within an account.<br><br>

##### Target Web Service 
 * [AccountSharedService](/docs/en/api_reference/services/AccountSharedService.md)
 * [SharedCriterionService](/docs/en/api_reference/services/SharedCriterionService.md)
 * [CampaignSharedSetService](/docs/en/api_reference/services/CampaignSharedSetService.md)
<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

#### 2.	Function improvement on Auto Bidding setting
Target Cost is available on creating auto bidding setting of "Maximize Clicks".<br>
<br>

##### Target Web Service 
 * [AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md)
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [BiddingStrategyService](/docs/en/api_reference/services/BiddingStrategyService.md)
<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

#### 3.	Add a selectable item on Ad Rotation (Optimization)
"Maximize conversions" is available on the setting "Ad Rotation" (Optimization) for campaign creation<br><br>

##### Target Web Service 
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

#### 4.	Expand available number of Landing Page URL
10 Landing Page URLs are available for each of ad, keyword and QuickLinks. It makes available to deal with Landing Page Optimization (LPO) such as A/B testing.<br><br>

##### Target Web Service 
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)
 * [AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md)

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

#### 5.	Function improvement on Ad Display Option
"Callout option" is added as optional description on QuickLinks of Ad Display Option.<br><br>

##### Target Web Service 
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)
 * [CampaignFeedService](/docs/en/api_reference/services/CampaignFeedService.md)
 * [AdGroupFeedService](/docs/en/api_reference/services/AdGroupFeedService.md)
<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

#### 6.	Added function upgrade
Partial function has been improved. Details are as follows:<br>

* Changes on WSDL namespace<br>
Following field names are changed.
<table>
<tr><th>Before</th><th>After</th></tr>
<tr><td rowspan="2">PlaceholderField</td><td>FeedItemPlaceholderField</td></tr>
<tr><td>FeedFolderPlaceholderField</td></tr>
<tr><td rowspan="4">PlaceholderType</td><td>FeedFolderPlaceholderType</td></tr>
<tr><td>FeedItemPlaceholderType</td></tr>
<tr><td>CampaignFeedPlaceholderType</td></tr>
<tr><td>AdGroupFeedPlaceholderType</td></tr>
<tr><td rowspan="4">BiddingStrategy</td><td>BiddingStrategy</td></tr>
<tr><td>CampaignBiddingStrategy</td></tr>
<tr><td>AdGroupBiddingStrategy</td></tr>
<tr><td>AdGroupCriterionBiddingStrategy</td></tr>
<tr><td rowspan="2">CriterionUse</td><td>CampaignCriterionUse</td></tr>
<tr><td>AdGroupCriterionUse</td></tr>
<tr><td rowspan="2">Settings</td><td>CampaignSettings</td></tr>
<tr><td>AdGroupSettings</td></tr>
</table>

* TrafficEstimatorService will sunset, because functions are similar to KeywordEstimatorService.
<br><br>


##### Target Web Service 
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)
 * [CampaignFeedService](/docs/en/api_reference/services/CampaignFeedService.md)
 * [AdGroupFeedService](/docs/en/api_reference/services/AdGroupFeedService.md)
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [FeedFolderService](/docs/en/api_reference/services/FeedFolderService.md)
 * [CampaignCriterionService](/docs/en/api_reference/services/CampaignCriterionService.md)
 * TrafficEstimatorService

<br><br>

##### Target Data Object and Enumeration 
 * Please confirm from data directory under API reference directory.
<br><br>

## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Before Ver.6.0</p>
</th>
<th valign="top">
  <p>Ver.6.1</p>
</th>
</tr>
<tr>
  <td colspan="3"><b>Sharing Negative Keywords</b></td>
</tr>
<tr>
 <td valign="top">AccountSharedService</td><td valign="top">Not supported</td><td valign="top">
New service</td>
</tr>
<tr>
<td valign="top">SharedCriterionService</td><td valign="top">Not supported</td><td valign="top">
New service</td>
</tr>
<tr>
<td valign="top">CampaignSharedSetService</td><td valign="top">Not supported</td><td valign="top">
New service</td>
</tr>
<tr>
  <td colspan="3"><b>Expand Auto bidding setting</b></td>
</tr>
<tr>
 <td valign="top">BiddingStrategyService</td><td valign="top">TargetSpend (Maximize clicks) supports click bid only</td><td valign="top">
TargetSpend (Maximize clicks) supports spendTarget (Target cost)</td>
</tr>
<tr>
  <td colspan="3"><b>Expand options of Optimization</b></td>
</tr>
<tr>
 <td valign="top">CampaignService</td><td valign="top">CONVERSION_OPTIMIZE is not available</td><td valign="top">
CONVERSION_OPTIMIZE is supported</td>
</tr>
<tr>
  <td colspan="3"><b>Expand available Landing Page URLs</b></td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td><td valign="top">Add/edit/delete/browse LPO are not available</td><td valign="top">
Add/edit/delete/browse LPO</td>
</tr>
<tr>
 <td valign="top">FeedItemService</td><td valign="top">Add/edit/delete/browse LPO are not available</td><td valign="top">
Add/edit/delete/browse LPO</td>
</tr>
<tr>
 <td valign="top">AdGroupCriterionService</td><td valign="top">Add/edit/delete/browse LPO are not available</td><td valign="top">
Add/edit/delete/browse LPO</td>
</tr>
<tr>
  <td colspan="3"><b>Improve Ad Display option</b></td>
</tr>
<tr>
 <td valign="top">FeedItemService</td><td valign="top">Setup/reference Callouts are not available</td><td valign="top">Setup/reference Callouts</td>
</tr>
<tr>
 <td valign="top">CampaignFeedService</td><td valign="top">Setup/reference Callouts are not available</td><td valign="top">Setup/reference Callouts</td>
</tr>
<tr>
 <td valign="top">AdGroupFeedService</td><td valign="top">Setup/reference Callouts are not available</td><td valign="top">Setup/reference Callouts</td>
</tr>

<tr>
  <td colspan="3"><b>Function upgrade</b></td>
</tr>
<tr>
 <td valign="top">FeedItemService</td><td valign="top">No impact</td><td valign="top">Enum name change</td>
</tr>
<tr>
 <td valign="top">AdGroupCriterionService</td><td valign="top">No impact</td><td valign="top">Enum name change</td>
</tr>
<tr>
 <td valign="top">CampaignFeedService</td><td valign="top">No impact</td><td valign="top">Enum name change</td>
</tr>
<tr>
 <td valign="top">AdGroupFeedService</td><td valign="top">No impact</td><td valign="top">Enum name change</td>
</tr>
<tr>
 <td valign="top">AdGroupService</td><td valign="top">No impact</td><td valign="top">Enum / Entity name change</td>
</tr>
<tr>
 <td valign="top">CampaignCriterionService</td><td valign="top">No impact</td><td valign="top">Enum name change, Entity configuration change</td>
</tr>
<tr>
 <td valign="top">FeedFolderService</td><td valign="top">No impact</td><td valign="top">Enum name change</td>
</tr>
<tr>
 <td valign="top">TrafficEstimatorService</td><td valign="top">No impact</td><td valign="top">Deleted</td>
</tr>

</table>

## Sunset Date of Older Version of Sponsored Search API
* Following versions will end support after the Advanced URL upgrade period (October 2016 or later).<br>
・Sponsored Search API Ver.5.1<br>
・Sponsored Search API Ver.5.2<br>
・Sponsored Search API Ver.5.3<br>
<br>
