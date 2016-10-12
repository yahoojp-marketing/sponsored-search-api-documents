# Release Note
Sponsored Search API Ver.6.2<br>

## Release version
6.2 (WSDL version : 6.2.0)

## Type of version up
Minor version up  

## Main features enhancement on the release
*Target objects and Enumeration are available on the list of Data Object (Enumeration).
<br><br>

#### 1. Add "Extended Text Ads" feature
"Extended TExt Ads" which supports 2 lines Title and 1 line Description is now available.<br>
It enables ad delivery with much information and large width more than usual.<br><br>

##### Target Web Service 
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
<br><br>

#### 2.	Function improvement on Bid Adjustment rate for devices
Bid adjustment rate can be set for each device, such as PC, Tablet or Smartphone. It is available by campaign or ad group level.<br><br>

##### Target Web Service 
 * [CampaignTargetService](/docs/en/api_reference/services/CampaignTargetService.md)
 * [AdGroupBidMultiplierService](/docs/en/api_reference/services/AdGroupBidMultiplierService.md)
<br><br>

#### 3.	Function update on Converion Count
Following data items are updated on counting conversion.
* Conversion tag issued when specified "One-per-click" or "Many-per-click" for counting type.
* Conversion tag issued when excluded from auto bidding.
* Counting period change (it has been fixed as 30 days, but now it can be specified between 7 to 90 days).
* Actual conversion value (response) change.
<br><br>

##### Target Web Service 
 * [ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md)
<br><br>

#### 4. Additional upgrades
* Following conditions are available on creating report definition.<br>
 - Includes "0 impression" data to output target of reporting.<br>
 - Includes deleted entities to output target of reporting.<br>
 
* Device Targeting Report sunset.
<br><br>

##### Target Web Service
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
<br><br>


## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.6.1 or before</p>
</th>
<th valign="top">
  <p>Ver.6.2</p>
</th>
</tr>
<tr>
  <td colspan="3"><b>Enhancement for "Extended Text Ads"</b></td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td><td valign="top">No change.</td><td valign="top">
・Can Add/Browse Extended Text Ads<br>
・Updates some objects<br>
-Added ExtendedTextAd<br>
-Deleted MobileAd
</td>
</tr>
<tr>
  <td colspan="3"><b>Function improvement on Bid Adjustment rate for devices</b></td>
</tr>
<tr>
 <td valign="top">CampaignTargetService</td><td valign="top">Bid adjustment is available on Smartphone only (by campaign) </td>
 <td valign="top">Can add and browse Bid adjustment setting for each device, PC, Tablet and Smartphone (by campaign)</td>
</tr>
<tr>
 <td valign="top">AdGroupBidMultiplierService</td><td valign="top">Bid adjustment is available on Smartphone only (by ad group)</td>
 <td valign="top">
・Can add and browse Bid adjustment setting for each device, PC, Tablet and Smartphone (by ad group)<br>
・Delete following objects<br>
　-BidMultiplierList<br>
　-PlatformBidMultiplierList<br>
　-PlatformBidMultiplier<br>
　-BidMultiplierType<br>
</td>
</tr>

<tr>
  <td colspan="3"><b>Additional items on Converion Count</b></td>
</tr>
<tr>
 <td valign="top">ConversionTrackerService</td>
 <td valign="top">
 ・Cannot get/set countingType<br>
 ・Cannot specify whether including to auto bidding<br>
 ・Counting period of conversion is fixed as 30days
</td>
<td valign="top">
・Can get/set countingType<br>
・Can specify whether include/exclude to auto bidding<br>
・Can specify the counting period between 7 to 90 days<br>
  *For App download campaign, it is fixed as 30days<br>
・Updated following items on actual conversion value (response)<br>
　-Added totalAllConversions as new<br>
　-Added totalAllConversionValue as new<br>
　-Added allConversions as new<br>
　-Addedd allConversionValue as new<br>
　-Changed numConversionEvents to conversions<br>
　-Changed totalNumConversionEvents to totalConversions<br>
　-Deleted totalNumConvertedClicks<br>
　-Deleted numConvertedClicks<br>
・Updated some objects<br>
　-Added ConversionCountingType<br>
　-Added ExcludeFromBidding<br>
　-Deleted HttpProtocol
</td>
</tr>
<tr>
  <td colspan="3"><b>Additional upgrades</b></td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">
 ・Setting whether includes "0 impression" is only available on filters<br>
 ・Cannot specify whether there is deleted entity or not on report output definition
</td>
<td valign="top">
・Including "0 impression" data to output target of reporting is available on report definition setting<br>
・Including deleted entities to output target of reporting is available on report definition setting<br>
・Device Targeting report closed.
</td>
</tr>
</table>
