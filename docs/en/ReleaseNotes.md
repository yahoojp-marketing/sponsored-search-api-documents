# Release Note
Sponsored Search API Ver.6.5<br>

## Release version
6.5 (WSDL version : 6.5.0)

## Type of version up
Minor version up  

## Main features enhancement on the release
&lowast;Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations).
<br><br>

#### 1. Conversion tracking across different devices (Website and click-to-call)
Conversions is tracked based on the user login information along with the existing cookie information.<br>
This enhancement will enable you to track conversions across different devices such as the case when the product was bought on smartphone after the ad was clicked on PC.<br>
The following enhancements have been updated:
1. The flag to control conversions across different devices has been added.
1. The report field used for conversion tracking has been added.

##### Target Web Service 
 * [ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md)
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
<br><br>

#### 2. Ad rotation setting by ad groups
Ad rotation setting has been changed from campaign level to ad group level.<br>
The following enhancements have been updated:
1. The items for adGroupAdRotationMode were added.<br>The following two values are available for 'ad rotation' items.
    - OPTIMIZE：Optimizes and display ads
    - ROTATE_FOREVER：Always rotates ads evenly (not optimized)
1. The item for the campaign’s have become read-only.<br>
    - On creating a new campaign, “OPTIMIZE” is evenly set to the 'ad rotation' item.<br>For this reason, if other enumeration besides "OPTIMIZE" is specified, it will be changed to "OPTIMIZE" when creating a new campaign.
    - On updating a campaign, even if you set a value when updating the campaign, the existing setting will be responded. It cannot be updated with any other enumuration.
1. The option "OPTIMIZE" is applied on ad distribution if the enumerations below have been set  for the item "adServingOptimizationStatus" on campaign. 
    - ROTATE
    - CONVERSION_OPTIMIZE

*Above changes 2 and 3 have been applied to the lower versions (Ver.6.4.0/6.3.0) similarily. 

##### Target Web Service  
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
<br><br>

#### 3. App Conversion Tracking Settings
At the time of conversion tracking for Mobile app download campaigns, you cannot select “Include” (Use conversion for Auto Bidding) for both “Download” and “App First Open” for the same package.<br>
The following enhancements have been updated:
1. A validation has been added so that an error occurs when the following two operations are performed.
    - The case if you select two settings below for the same ‘appId’ (application ID) at a time:<br>
      App conversion types: “Download”, “Use for auto bidding”<br>
      App conversion types: “App First Open”, “Use for auto bidding”
    - The case if you select “App First Open” AND “Use for auto bidding” for conversion setting without the settings both “Download” and “Do not use for auto budding” on App conversion type in advance for the same ‘appId’:
1. You are able to search the conversion settings of app using the ‘appId’.

*Above change 1 has been applied to the lower versions (Ver.6.4.0/6.3.0) similarily.

##### Target Web Service  You will be able to search the conversion settings of app using the ‘appId’.
 * [ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md)
<br><br>

## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
Ver.6.4 or before
</th>
<th>
Ver.6.5
</th>
</tr>
<tr>
 <td valign="top">ConversionTrackerService</td>
 <td valign="top">No change in API IF.<br>*Error codes have been added.</td>
 <td valign="top">
  ・The flag 'CrossDeviceConversionFlag' to control conversions across different devices has been added.<br>
  ・Conversion settings for app can be searched by application ID (appId).<br>
  ・Error codes have been added.
  </td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">No change in API IF.<br>*Report fields have been added.</td>
 <td valign="top">No change in API IF.<br>*Report fields have been added.</td>
</tr>
<tr>
 <td valign="top">CampaignService</td>
 <td valign="top">
  ・The item for the campaign’s ‘adServingOptimizationStatus’ has become read-only.<br>
  ・On the request of ADD/SET, 'adServingOptimizationStatus' is 'Ignore'.<br>
  ・On the response of ADD/SET, the responded enumuration to 'adServingOptimizationStatus' is 'OPTIMIZE' for ADD case, and the existing enumuration which has been already set is for SET case.
 </td>
 <td valign="top">
  ・The item for the campaign’s ‘adServingOptimizationStatus’ have become read-only.<br>
  ・On the request of ADD/SET, 'adServingOptimizationStatus' is 'Ignore'.<br>
  ・On the response of ADD/SET, the responded enumuration to 'adServingOptimizationStatus' is 'OPTIMIZE' for ADD case, and the existing enumuration which has been already set is for SET case.
  </td>
</tr>
<tr>
 <td valign="top">AdGroupService</td>
 <td valign="top">No change in API IF.<br>*Ad rotation (optimization) setting is not available for ADD/SET/GET.</td>
 <td valign="top">
  ・'AdGroupAdRotationMode' has been added.<br>
  ・Ad rotation (optimization) setting by ad group is available for ADD/SET/GET.</td>
</tr>
<tr>
 <td valign="top">CampaignRetargetingListService</td>
 <td valign="top">No change in API IF.<br>*Error codes have been added.</td>
 <td valign="top">No change in API IF.<br>*Error codes have been added.</td>
</tr>
<tr>
 <td valign="top">AdGroupRetargetingListService</td>
 <td valign="top">No change in API IF.<br>*Error codes have been added.</td>
 <td valign="top">No change in API IF.<br>*Error codes have been added.</td>
</tr>
</table>

## The end scheduled date for Sponsored Search API 6.3
Sponsored Search API 6.3 is scheduled to sunset on the end of March, 2018<br>
<br>

