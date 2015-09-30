# Release Notes
Sponsored Search API ver.5.2
## Release version
5.2 (WSDL Version: 5.2.0)
## Types of Version update
Minor version up  
※Refer to the URL below for the type of version upgrade.
## Main contents of this release

#### 1. Added Data Auto Insertion function
Function of submitting the data of product information to the ads has been added.  
In addition, function of displaying the remaining time (countdown) has been added.  
  
##### To submit ads, the setting can be done as follows.
* Data Insertion function  

> Title: **{=vacuum.model}** 販売  
> Display URL: www.example.com  
> Description 1: **{=vacuum.price}** からご用意！  
> Description 2: 日本全国どこでも配送料無料  

* Countdown function  

> Title: 掃除機セール中  
> Display URL: www.example.com  
> Description 1: 半年に一回のチャンス！  
> Description 2: セール終了まであと**{=COUNTDOWN(vacuum.sales ends,"ja",5)}**  

*Specify the list on the first parameter, and specify the number of days before to start the countdown on the third parameter (It will be "5" days before on the example).  
  
*For Countdown, it is possible to submit the date and time directly.  
  
> Title: 掃除機セール中  
> Display URL: www.example.com  
> Description 1: 半年に一回のチャンス！  
> Description 2: セール終了まであと**{=COUNTDOWN(2015/01/15 09:00:00,"ja",5)}**  

##### If the first row of the data is chosen to display as ad, the submitted data insertion and countdown ads will be displayed as follows.  

* Setting example of the list for data insertion and countdown  
<table class="standard">
<tbody><tr>
<th rowspan="2" valign="top">
  <p>List name</p>
</th>
<th colspan="3" valign="top">
  <p>Column name</p>
</th>
<th rowspan="2" valign="top">
  <p>Target campaign</p>
</th>
<th rowspan="2" valign="top">
  <p>Target ad group</p>
</th>
</tr>
<tr>
<th valign="top">
  <p>model</p>
</th>
<th valign="top">
  <p>price</p>
</th>
<th valign="top">
  <p>sales ends</p>
</th>
</tr>
<tr>
<td rowspan="3" valign="middle">
  <p></p><center>vaccum</center><p></p>
</td>
<td valign="top">
  <p></p><center>ルンバ630</center><p></p>
</td>
<td valign="top">
  <p></p><center>32,000円</center><p></p>
</td>
<td valign="top">
  <p></p><center>2015/01/15</center><p></p>
</td>
<td valign="top">
  <p></p><center>掃除機_海外</center><p></p>
</td>
<td valign="top">
  <p></p><center>ロボット掃除機</center><p></p>
</td>
</tr>
<tr>
<td valign="top">
  <p></p><center>ダイソンDC61</center><p></p>
</td>
<td valign="top">
  <p></p><center>29,000円</center><p></p>
</td>
<td valign="top">
  <p></p><center>2015/01/20</center><p></p>
</td>
<td valign="top">
  <p></p><center>掃除機_海外</center><p></p>
</td>
<td valign="top">
  <p></p><center>ハンディ掃除機</center><p></p>
</td>
</tr>
<tr>
<td valign="top">
  <p></p><center>トルネオVC-RV1</center><p></p>
</td>
<td valign="top">
  <p></p><center>59,800円</center><p></p>
</td>
<td valign="top">
  <p></p><center>2015/02/23</center><p></p>
</td>
<td valign="top">
  <p></p><center>掃除機_国内</center><p></p>
</td>
<td valign="top">
  <p></p><center>ロボット掃除機</center><p></p>
</td>
</tr>
</tbody></table>


* Data Insertion function

> **ルンバ630** 販売  
> www.example.com  
> **32,000円** からご用意！日本全国どこでも配送料無料  

* Countdown function

（If the ads are shown in 2015/01/13）  

> 掃除機セール中  
> www.example.com  
> 半年に一回のチャンス！セール終了まであと**2日**  
  
##### Specifying the target depends on the purpose in where to set. The table of the setting is as follows.

<table class="standard">
<tbody><tr>
<th valign="top">
  <p>Purpose</p>
</th>
<th valign="top">
  <p>Target campaign</p>
</th>
<th valign="top">
  <p>Target ad group</p>
</th>
<th valign="top">
  <p>Target keyword</p>
</th>
<th valign="top">
  <p>Match type</p>
</th>
</tr>
<tr>
<td valign="top">
  <p>Specific campaign</p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p> </p>
</td>
<td valign="top">
  <p> </p>
</td>
<td valign="top">
  <p> </p>
</td>
</tr>
<tr>
<td valign="top">
  <p>Specific ad group</p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p> </p>
</td>
<td valign="top">
  <p> </p>
</td>
</tr>
<tr>
<td valign="top">
  <p>Specific keyword under specific campaign</p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p> </p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
</tr>
<tr>
<td valign="top">
  <p>Specific keyword under specific ad group</p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
<td valign="top">
  <p></p><center>Req</center><p></p>
</td>
</tr>
</tbody>
</table>

*There is no restriction in setting the target entities on each list data.<br>
*The entites from the sample signifies as follows:<br>
　・List name：feedFolder<br>
　・Column name：feedAttribute<br>
　・Target campaign：targetCampaign<br>
　・Target ad group：targetAdGroup<br>
<br>
* Target Web Service  
 * [AdGroupFeedService](/docs/en/api_reference/services/AdGroupFeedService.md)
 * [FeedItemService](/docs/en/api_reference/services/FeedItemService.md)
 * [FeedFolderService](/docs/en/api_reference/services/FeedFolderService.md)
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
  
* Target Data Object  
 * Please confirm from the Entities document of each Services attached to the document folder
  
* Target Enumerations  
 * Please confirm from the Enumerations document of each Services attached to the document folder.
  
#### 2. Function improvement from Auto bidding release
Submitting by intersecting the ad group is available.  
Ad types are added to the selector of ad group.  
The maximum number of request has been changed.  
  
* Target Web Service
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
  
* Target Data Object  
 * Please confirm from the Entities document of each Services attached to the document folder
  
* Target Enumerations  
 * Please confirm from the Enumerations document of each Services attached to the document folder.

#### 3. Impact on each Version from the change of Services

<table class="standard">
<tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.5.1 or before</p>
</th>
<th valign="top">
  <p>Ver.5.2</p>
</th>
</tr>
<tr>
<td valign="top">
  <p>AdGroupAdService</p>
</td>
<td valign="top">
  <p>- No change in APIIF</p>
</td>
<td valign="top">
  <p>- APIIF changed<br>
・adTypes is added to AdGroupAdSelector<br>
・Maximum number of response per request has been changed in some fields.<br>
・Added feedFolderId to AdGroupAd.<br>
・Added displayUrl to Ad.<br>
<br>
■Error messages<br>
・"210122：Non existing feed has been set." will return if non-existing feed is set.<br>
・"210601：Multiple feeds are set in one ad." will return if multiple feeds are set in one ad.<br>
・"210602：Insertion is over the limit." will return if the insert method is not valid or over the maximum limit.<br>
　* This will be the change of "20701：INVALID_STRING_FORMAT" up to Ver.5.1.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>FeedItemService</p>
</td>
<td valign="top">
  <p>- No change in APIIF<br>
・Cannot make Data auto insertion setting.</p>
</td>
<td valign="top">
  <p>- APIIF changed<br>
・targetingCampaign, targeting AdGroup, and targetingKeyword are added for Data auto insertion<br>
<br>
■Error messages<br>
・"210122：Non existing feed has been set." will return if non-existing feed is set.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>FeedFolderService</p>
</td>
<td valign="top">
  <p>- Not supported</p>
</td>
<td valign="top">
  <p>- New Service<br>
・FeedFolder and FeedAttribute are added to operate the List for Data auto insertion.<br>
<br>
■Error messages<br>
・"210122：Non existing feed has been set." will return if non-existing feed is set.</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>ReportDefinitionService</p>
</td>
<td valign="top">
  <p>- No change in APIIF</p>
</td>
<td valign="top">
  <p>- APIIF changed<br>
・feedFolderIds is added to ReportDefinition for the performance report for Data auto insertion.</p>
</td>
</tr>
</tbody>
</table>

## Technical reference
This release information is written in Sponsored Search API Ver.5.2.  

## Regarding the older version of Sponsored Search API  
You still can use older version (Ver.5.1 and below) of Sponsored Search API.  

## Older Version Sunset Date  
Sponsored Search API Ver.5.0 will sunset after September 2015.  
* We will inform once again, when the date is fixed.

