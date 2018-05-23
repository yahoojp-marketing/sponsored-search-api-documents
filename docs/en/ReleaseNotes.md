# Release Notes
Sponsored Search API V201805

## Release version
V201805 (WSDL Version: V201805)

## Main contents of this release
*For Target Data object and Enumuration, please confirm from data directory under API reference directory. 

#### 1. Change on releasing and numbering new versions
#### (1) Releasing new versions on regular basis
The new version has been released on regular basis as follows.

< Before change >
* The timing of the release:<br>
A new API version was released for every system enhancement
* Version numbering: <br>
VX.X (example: V6.5)

< After the change of V201805 >
* The timing of the release:<br>
Some enhancements in a certain period will be released in bulk<br>
*We will inform the closing of the oldest available version on a new version release.
* Version numbering: <br>
VYYYYMM (example: V201805)

#### (2) Change on version numbering
In order to clear duplicating entities issue because of auto generation in some environment, we made a NameSpace classification and the object architecture change.

* For more detail, please confirm "[Change on version numbering and wsdl configuration](/docs/en/api_reference/appendix/numbering_new_versions.md)"

### 2. ‘Category Text’ of Ad Display Option
A new feature “Category Text” has been added to ad display options on Sponsored Search API.<br>
Category Text will add supplementary categories (headers) and texts (phrases) to your ads that match the characteristics of your product or service.<br>

1. Following operations became available by the release of Category Text feature mainly.<br>
‐ Craete, edit, remove Category Text and refer the settings.<br>
‐ Make and release a setup setting to campaign(s) and/or ad group(s), and refer the settings.<br>
‐ Acquire operation history data 
2. New report fields related to Category Text have been added.

** Above 2. will be also applied to the earlier versions (Ver.6.5.0 and 6.4.0).

##### Target Web Service   
 * [FeedItemServcie](/docs/ja/api_reference/services/FeedItemServcie.md)
 * [CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md)
 * [AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

### 3. System updates
Feature enhancement for acquiring reasons of system close on Target List of Site Retargeting, and some system updates.<br>
Please confirm the details at the part of 'Impact on each Version from the change of Services' below. 

##### Target Web Service 
 * [FeedItemServcie](/docs/ja/api_reference/services/FeedItemServcie.md)
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)
<br>

## Impact on each Version from the change of Services
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
Ver.6.5 or before
</th>
<th>
V201805
</th>
</tr>
<tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">
  ・Added the following Enumerations to placeholderType.<br>
  　‐STRUCTURED_SNIPPET (Category Text)<br>
  ・Added the following Enumerations to FeedItemPlaceholderField.<br>
  　‐STRUCTURED_SNIPPET_HEADER (Category Text - Category)<br>
  　‐STRUCTURED_SNIPPET_VALUES (Category Text - Text)<br>
  ・Deleted 'Advanced (a flag for AdvancedURL)' from selector/operand.<br>
  ・Added 'NONE (not specified)' to DevicePreference (Focus device).
 </td>
</tr>
<tr>
 <td valign="top">CampaignFeedService</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">Added the following Enumerations to placeholderType.<br>
 　‐STRUCTURED_SNIPPET (Category Text)<br></td>
</tr>
<tr>
 <td valign="top">AdGroupFeedService</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">Added the following Enumerations to placeholderType.<br>
 　‐STRUCTURED_SNIPPET (Category Text)<br></td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">No change in API IF.<br>
 * Added report fields.</td>
 <td valign="top">No change in API IF.<br>
 * Added report fields.</td>
</tr>
<tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">Added closingReason (the reason of Target List closed).</td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">Deleted 'Advanced (a flag for AdvancedURL)' from selector/operand.</td>
</tr>
<tr>
 <td valign="top">AdGroupCriterionService</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">Deleted 'Advanced (a flag for AdvancedURL)' from selector/operand.</td>
</tr>
<tr>
 <td valign="top">All services</td>
 <td valign="top">No change in API IF.</td>
 <td valign="top">
     ・Change on version numbering<br>
     ・Change on wsdl configuration (Namespace fragmentation)</td>
</tr>
</table>

## Sunset schedule of Sponsored Search API Ver.6.4
Sponsored Search API Ver.6.4 is scheduled to sunset as follows.  
* Support closing on : June 23, 2018.<br>
* System closing on : July 23, 2018.<br>
