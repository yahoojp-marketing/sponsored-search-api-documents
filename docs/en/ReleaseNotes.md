# Release Notes
Sponsored Search API V201909

## Release version
V201909 (WSDL Version: V201909)

## Main contents of this release
*For Target Data object and Enumuration, please confirm from data directory under API reference directory.

### 1. Trademark restriction of ad text by trademark owner
Checking whether the trademark restriction has been removed for ads and QuickLinks, became available. It is able to be checked in bulk. <br>
When the trademark restriction has been removed, a value that describes “removed” will return on “AdGroupAdService” and on “FeedItemService.” <br>
This was released in May 2019 on the Campaign Management Tool. See the following announcement for the details. <br>
[Trademark restriction started](https://promotionalads.yahoo.co.jp/support/release/674122.html#article_en)<br>

##### Target Web Service
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)

### 2. Removing “Target position in search results”
“PageOnePromotedBiddingScheme” (for Target position in search results) has been removed. <br>
It has closed in April 2019 on the Campaign Management Tool. See the following announcement for the details. <br>
[“Target position in search results” closed](https://promotionalads.yahoo.co.jp/support/release/659760.html#article_en)

##### Target Web Service
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [BiddingStrategyService](/docs/en/api_reference/services/BiddingStrategyService.md)

### 3. Removing the report index “Avg. Position”
The reporting field “AVG_DELIVER_RANK” (for Average position) has been removed. The value will be acquired and appear as "--" (double hyphen) after the closing date. <br>
When adding and editing Tracking URL and etc., {adposition} is not available. Tracking adposition on existing parameters becomes unavailable, and empty string will return.  There is no effect on ad delivery. <br>
See the following reference for {adposition} of Tracking URL in detail. <br>
[Tracking Parameter](https://github.com/yahoojp-marketing/sponsored-search-api-documents/blob/201901/docs/en/api_reference/appendix/tracking.md)<br>
See the following announcement for the details. <br>
[Closing index in performance data](https://promotionalads.yahoo.co.jp/support/release/713854.html#article_en)

##### Target Web Service
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)

### 4. Removing a setting item of Auto Bidding Type
The item “spendTarget” of “TARGET_SPEND” (for Auto bidding type : Maximize Clicks) that is available for Auto bidding Type “Portfolio bidding” has been  removed.
Note that if you set “spendTarget” on the lower version (V201808, V201901), validation error occurs.
It has closed on July 25, 2019 on the Campaign Management Tool. See the following announcement for the details. <br>
[Closing some items of Auto bidding setting](https://promotionalads.yahoo.co.jp/support/release/683185.html#article_en)

##### Target Web Service
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [BiddingStrategyService](/docs/en/api_reference/services/BiddingStrategyService.md)

### 5. Integrating “ReportService” with “ReportDefinitionService”
“ReportService” has been integrated with “ReportDefinitionService”. Periodic reports became unavailable with this integration. <br>
On December 19, 2019, “intervalType” on periodic reports of earlier versions (V201808, V201901) will be changed to “ONETIME”. After this change, all periodic reports will not run. <br>
Learn about details on the following document. <br>
 * [Reference](https://github.com/yahoojp-marketing/sponsored-search-api-documents/blob/201909_reportdefinition/docs/en/api_reference/services/ReportDefinitionService.md)<br>
 * [Best Practice](https://github.com/yahoojp-marketing/sponsored-search-api-documents/tree/201909_reportdefinition/docs/en/bestpractice)<br>

##### Target Web Service
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)

### 6. Ad Display Option enhancement
 * Expanded QuickLinks release<br>
 Adding description texts to QuickLinks becomes available (Expanded QuickLinks). 
 Following items are added to “FeedItemPlaceholderField”. <br>
 ・ LINK_DESCRIPTION_1 : QuickLink description 1<br>
 ・ LINK_DESCRIPTION_2 : QuickLink description 2<br>
Both “LINK_DESCRIPTION_1” and “LINK_DESCRIPTION_2” are required when using QuickLink description feature. 
If setting either of these descriptions, it will be an error. <br>
 * Target Devices unavailable<br>
 The setting item "Target Devices" for Ad display option setup will be closed. As a result, “DevicePlatform” on “CampaignFeed” and “AdGroupFeed” will become unavailable after October 2, 2019.
　　 Around early December 2019, “DevicePlatform” will close. <br>
The release on the Campaign Management Tool is scheduled on October 2, 2019. See the following announcement for the details. <br>
 [Sponsored Search QuickLinks additional feature](https://biz.marketing.yahoo.co.jp/developercenter-en/announcement/752120/)

##### Target Web Service
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)

### 7. Maintenance Release
 * Updated WSDL “AuditLogService”.
 * Closed “LocationService”.
 * Added “feedFolderId” to “FeedItem” as search criteria.
 * Acquiring operation history including actions on the Campaign Management Tool became available on API.
※ Please confirm the details at the part of 'Impact on each Version from the change of Services' below. 

##### Target Web Service 
 * [AuditLogService](/docs/en/api_reference/services/AuditLogService.md)
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)

## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
 <tr>
 <th>Service</th>
 <th>Before V201901</th>
 <th>V201909</th>
 </tr>
 <tr>
 <td valign="top">CampaignService</td>
 <td valign="top">
 ・When setting “Target Position in search results” (PageOnePromotedBiddingScheme) on bidding setting, validation error occurs.<br>
 ・When setting "Target Daily Budget” (spendTarget), validation error occurs.<br>
 </td>
 <td valign="top">
 ・Removed “PageOnePromotedBiddingScheme” (for Target position in search results).<br>
 ・The item “Target Daily Budget” (spendTarget) will be removed.
 </td>
 </tr>
 <tr>
 <td valign="top">BiddingStrategyService</td>
 <td valign="top">
 ・When setting “Target Position in search results” (PageOnePromotedBiddingScheme) on bidding setting, validation error occurs<br>
 ・When setting "Target Daily Budget” (spendTarget), validation error occurs.
 </td>
 <td valign="top">
 ・Removed “Target Position in search results” (PageOnePromotedBiddingScheme) on bidding setting.<br>
 ・Removed the item “Target Daily Budget” (spendTarget).
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">
 ・Checking whether the restriction has been removed in bulk is unavailable.<br>
 </td>
 <td valign="top">
 ・Checking whether the restriction has been removed in bulk is available.<br>
 </td>
 </tr>
 <tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">
 ・Checking whether the restriction has been removed in bulk is unavailable.<br>
 ・Specifying feedFolderId as search criteria is unavailable.
 </td>
 <td valign="top">
 ・Checking whether the restriction has been removed in bulk is available.<br>
 ・Specifying feedFolderId as search criteria is available.
 </td>
 </tr>
 <tr>
 <td valign="top">AuditLogService</td>
 <td valign="top">
 ・When setting with minimum value, validation error occurs.<br>
 ・Acquiring operation history on the Campaign Management Tool is unavailable.
 </td>
 <td valign="top">
 ・When setting with minimum value, validation error occurs. (There is no effect since only the validation part is different) .<br>
 ・Acquiring operation history on the Campaign Management Tool is available.
 </td>
 </tr>
 <tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">
 ・Create a report by using ReportDefinitionService/ReportService.<br>
 ・Creating periodic reports is available.<br>
 ・Selecting Avg. Position is available.
 </td>
 <td valign="top">
 ・Create a report using ReportDefinitionService only.<br>
 ・Creating periodic reports is unavailable.<br>
 ・Selecting Avg. Position is available, however its value appears as "--" (double hyphen).
 </td>
 </tr>
 <tr>
 <td valign="top">ReportService</td>
 <td valign="top">
 ・Create a report by using ReportDefinitionService/ReportService.<br>
 ・The value of Avg. Position appears as “--” (double hyphen).
 </td>
 <td valign="top">
 ・Integrating ReportService with ReportDefinitionService.
 </td>
 </tr>
 <tr>
 <td valign="top">LocationService</td>
 <td valign="top">
 ・Using LocationService is optional.
 </td>
 <td valign="top">
 ・Closed LocationService.
 </td>
 </tr>
</tbody>
</table>

## Sunset schedule of Sponsored Search API V201808
Sponsored Search API V201808 is scheduled to sunset as follows.
* Deprecation Date (Support closing on) : October 17, 2019<br>
* End of Life Date (System closing on) : December 19, 2019<br>
