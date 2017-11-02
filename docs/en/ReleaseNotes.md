# Release Note
Sponsored Search API Ver.6.4<br>

## Release version
6.4 (WSDL version : 6.4.0)

## Type of version up
Minor version up  

## Main features enhancement on the release
&lowast;Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations).
<br><br>

#### 1. "Ad Customizer" feature enhancement
The following enhancements have been updated with Ad Customizer.

 * It supports Geo Targeting in data auto insertion list units.
 * When using Ad Customizer, it is no longer necessary to create Ads. Ad Customizer is only available for a set of insertion ads and data auto insertion list.
 * It supports "IF function". By using the IF function in insertion ads, ad text for smartphone is able to be displayed automatically when the device is a smartphone.
 * To increase the number of data auto insertion list from 400 thousand to 1 million per account.<br>

&lowast;Geo Targeting is the only change on the API interface.
For details of ad customizer, please refer to the following Help.<br>
<a href="https://help.marketing.yahoo.co.jp/en/?cat=476">Sponsored Search Help　Ad Customizer</a>
<br><br>

##### Target Web Service   
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
<br><br>

#### 2.	Additional upgrades
Following web services have been updated.<br>
More change details are referable on the matrix of 'Impact on each version from the change of services' below.
<br>
<br>

##### Target Web Service
 * [CampaignExportService](/docs/ja/api_reference/services/CampaignExportService.md)
 <br><br>

## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
Ver.6.3 or before
</th>
<th>
Ver.6.4
</th>
</tr>
<tr>
  <td colspan="3"><b>1.	"Ad Customizer" feature enhancement</b></td>
</tr>
<tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">No change</td>
 <td valign="top">
・It supports Geo Targeting(Target Location) in data auto insertion list units.
<br>
・Added Location object.<br>
・Added the following Enumerations.<br>
　- FeedItemGeoRestriction<br>
　- CriterionTypeFeedItem<br>
・Added error codes.
 </td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">No change</td>
 <td valign="top">Added error codes.
 </td>
</tr>
<tr>
  <td colspan="3"><b>2.	Additional upgrades</b></td>
</tr>
<tr>
 <td valign="top">CampaignExportService</td>
 <td valign="top">No change</td>
 <td valign="top">
・Searching job status by "get" operation is available. And, Job ID specification was changed from required to optional.<br>
・Specifing the field to be exported by "addJob" is allowed.<br>
・New "getExportFields" has been released. It enables to inquire exportable fields.<br>
・Added the following Enumerations.<br>
　- CampaignExportFieldAttribute<br>
　- CampaignExportFieldValue<br>
・Deleted Advanced object.<br>
 </td>
</tr>
</table>

## The end scheduled date for Sponsored Search API 6.2
Sponsored Search API 6.2 is scheduled to sunset on January 24, 2018 (Wed) JST.<br>
<br>
