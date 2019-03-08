# SOAP faults
List of SOAP error code and message when the error or problem occurs.

### Overview
If your SOAP request is successful, the Sponsored Search API will return an HTTP 200 OK response code and the SOAP response. <br> If an error occurs during the processing of your SOAP request, Sponsored Search API will return an error code and message. <br>See [Error](/docs/en/api_reference/data/Common/Error.md), [ErrorDetail](/docs/en/api_reference/data/Common/ErrorDetail.md) for the entity details

### Sample Error Response

There are 3 types of SOAP error response, SAPFault, Full error and Part error. See the following description about each response.

#### SOAPFault

SOAPFault response returns for WSDL violation, SOAP syntax violation, system error and authentication error.<br>
The returned SOAPFault is in the any of following forms depending on the service.

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>0011</faultcode>
      <faultstring>Can not login.</faultstring>
      <faultactor/>
      <detail>
        <requestKey>apiAccountId</requestKey>
        <requestValue>xxxx-xxxx-xxxx-xxxx</requestValue>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header/>
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>SOAP-ENV:Client</faultcode>
      <faultstring xml:lang="en">0011:Can not login.</faultstring>
      <detail>
        <ApiExceptionFault xmlns="http://ss.yahooapis.jp/V201808/Account">{"details":[{"key":"license","value":["xxxx-xxxx-xxxx-xxxx"]},{"key":"apiAccountId",
        "value":["xxxx-xxxx-xxxx-xxxx"]}]}</ApiExceptionFault>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Full Error

Full Error is returned for the fail of entire request caused by request constraints, etc. It is different from SOAPFault.<br>
Part Error is returned for the request fail caused by constraints in each ‘<operand>’ of SOAP request.

The following response is an example of Full Error in the case of invalid ‘numberResults’ value of `Paging` in [AccountService](/docs/ja/api_reference/services/AccountService.md).

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Account" xmlns:xsi="http://www.w3
.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns2:ResponseHeader>
      <ns1:service>AccountService</ns1:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns2:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse>
      <ns2:error>
        <ns1:code>0007</ns1:code>
        <ns1:message>invalid number format.</ns1:message>
        <ns1:detail>
          <ns1:requestKey>numberResults</ns1:requestKey>
          <ns1:requestValue>1000000</ns1:requestValue>
        </ns1:detail>
      </ns2:error>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Part Error

Part Error is returned in the error case caused by constraints of each element in ‘<operand>’.<br>
Part Error is returned for each ‘<operand>’, whether an error occurred or not.<br>
The error response may contain both of ‘true’ and ‘false’ as value of ‘<operationSucceeded>’, since '<value>' returns for each '<operand>' when you send a single SOAP request which includes multiple ‘<operand>’.

The following response is an example of Part Error in the case of specifying a ‘reportId’ which does not exist in [ReportService](/docs/ja/api_reference/services/ReportService.md).

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Report" xmlns:xsi="http://www.w3
.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns2:ResponseHeader>
      <ns1:service>ReportService</ns1:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns2:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse>
      <ns2:rval>
        <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns2:values>
          <ns1:operationSucceeded>false</ns1:operationSucceeded>
          <ns1:error>
            <ns1:code>0010</ns1:code>
            <ns1:message>not a valid id.</ns1:message>
            <ns1:detail>
              <ns1:requestKey>reportId</ns1:requestKey>
              <ns1:requestValue>1234567890</ns1:requestValue>
            </ns1:detail>
          </ns1:error>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Error Codes
Sponsored Search API returns these SOAP faults when errors occur.
#### Common error

##### Service
All services.

 Code    | Message        | Description
-------- | -------------- | ------------------------
0001 | Invalid Request.  | This error can result for a variety of reasons. <br>Typically because one of the parameter values in the request is wrong or invalid and the operation cannot be completed.
0002 | An internal error has occurred.  | An internal error has occurred. Please try again later. <br>If the problem continues, please contact the support team via Inquiry page for assistance. <br>&lowast;Be sure to have your SOAP Request/Response ready.
0003 | Frequency limit exceeded. Please try your request again later. | Frequency limit exceeded. Please try your request again later.
0004 | Invalid location.  | Account cannot be accessed at this location. <br>Please use the LocationService to retrieve the URL prefix for the colocation the account is assigned to.
0011 | Can not login. | Login failed. <br>Please check whether the license key, API account, API account password are correct.<br> For OnBehalf account, OnBehalfOfPassword may be incorrect or it may not be associated with the requested account ID.
0013 | method is invalid. | The operation is not available. <br>This error may also result if you specified a operation which does not exist.
0014 | selector is invalid.  | The selector is invalid. <br>This error result if you specified multiple selector in your request body.
0015 | operations is invalid.  | The operation is invalid. <br>This error result if you specified multiple operation in your request body.
0016 | operator is invalid | This service does not support mutate operation.
0099 | Out of service.  | API is under maintenance or not available to use.
F0001  | Invalid format.   | The value format is invalid.
F0002  |	Invalid file format. | The upload file format is invalid.
R0001 | Require. | It is missing required parameter.
V0001 | Invalid value. | The value is invalid.
V0002 | Empty file. | The upload file is 0 byte.
V0003 | Over limit of the file. | The upload file size exceeds the limit.
L0001 | Lower list size. | The number of elements in the array is below the lower limit.
L0002 | Over list size. | The number of elements in the array exceeds the upper limit.
U0001 | Url has expired. | The upload URL or download URL has expired.
U0002 | Invalid url. | The upload URL or download URL is invalid.
S0001 | Invalid Status. | The status is invalid.
I0001 | Deactivated Id. | The ID is Deactivated.
D0001 | Duplicate. | The unique value is duplicated.
RL001 | Invalid relation. | The relation of the request is contradictory.<br> For example, you are specifying the date of start > end.
LT001 | Over limit. | The upper limit value that can be registered is exceeded.


#### Account, ConversionTracker, Retargeting Management error
##### Service
[AccountService](/docs/en/api_reference/services/AccountService.md),<br>
[AccountTrackingUrlService](/docs/en/api_reference/services/AccountTrackingUrlService.md),<br>
[ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md),<br>
[RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)

 Code    | Message        | Description
-------- | -------------- | ------------------------
210802| Adult account selected.| The adult account has been specified.
210803| Retargeting unavailable.| The account whose retargeting is forcibly stopped due to the review status.
210804| Registered default list.| The default list is registered again for the account with default list registered.
210806| Requires default list.| The rule list or the combination list is registered for the account for which no default list has been registered.
210807| Selecting Close default list.| "CLOSED" is specified in the target default list.
210809| Not logical target list.| The combination list is specified in the combination list.
210815| Selecting only one target list.| Only one target list is specified in the combination list.
210816| Selecting only Not condition.| Only the NOT condition is specified in the combination list.
210822| Cannot create a share target list. | If you do not have account sharing settings, you can not add share target list.
225303| Cannot duplicate Auto Bidding, since the app conversion type 'App Download' has been already with 'Auto' bidding on the same App ID. | If 'App Download' is set for the app conversion type with the same App ID, Auto Bidding can not be set twice.
225304| Invalid combination of Auto Bidding and the app conversion type 'App Download' on the same App ID. | With the same App ID, the combination of the app conversion type 'App Download' and Auto Bidding setting is incorrect.

#### Campaign Management error
##### Service
[AccountSharedService](/docs/en/api_reference/services/AccountSharedService.md), <br>
[AdGroupService](/docs/en/api_reference/services/AdGroupService.md),<br>
[AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md), <br>
[AdGroupBidMultiplierService](/docs/en/api_reference/services/AdGroupBidMultiplierService.md), <br>
[AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md),<br>
[AdGroupFeedService](/docs/en/api_reference/services/AdGroupFeedService.md),<br>
[AdGroupRetargetingListService](/docs/en/api_reference/services/AdGroupRetargetingListService.md),<br>
[BiddingStrategyService](/docs/en/api_reference/services/BiddingStrategyService.md),<br>
[CampaignService](/docs/en/api_reference/services/CampaignService.md),<br>
[CampaignExportService](/docs/en/api_reference/services/CampaignExportService.md), <br>
[CampaignFeedService](/docs/en/api_reference/services/CampaignFeedService.md),<br>
[CampaignRetargetingListService](/docs/en/api_reference/services/CampaignRetargetingListService.md),<br>
[CampaignCriterionService](/docs/en/api_reference/services/CampaignCriterionService.md), <br>
[CampaignSharedSetService](/docs/en/api_reference/services/CampaignSharedSetService.md), <br>
[CampaignTargetService](/docs/en/api_reference/services/CampaignTargetService.md),<br>
[FeedItemService](/docs/en/api_reference/services/FeedItemService.md),<br>
[SharedCriterionService](/docs/en/api_reference/services/SharedCriterionService.md)


コード                   | メッセージ  | 説明
------------------------ | ----------- | -------------------------------------------------------
210110| INVALID TARGET | The daily schedule specification exceeds the upper limit (6 cases).
210112| can not delete a PlatformTarget | The platform target can not deleted.
210113| can not modify a bidMultiplier | A bidMultiplier can not be modified.
210123| CAMPAIGN TARGETING MISMATCH | It can not be set because the campaign ID specified by targetingCampaignId is different from the campaign ID of the ad group specified by targetingAdGroupId.
210126| Mobile app download cannot connect to. | Mobile app download cannot connect to.
210127| Mobile app download cannot connect to Feed item.| Mobile app download cannot connect to Feed item.
210200| Auto bidding has been used. | The auto bidding can not be deleted because it is set to either campaign, ad group, or keyword.
210202| Auto bidding type does not match.  | Auto bidding type being registered does not match the requested auto bidding type.
210300| Double or no settings in Auto bidding.  | There is no specification of biddingStrategyType or biddingStrategyId. <br>Or both biddingStrategyType and biddingStrategyId are specified.
210301| Setting the disabled Auto bidding.  | Auto bidding in editing (including deletion) is specified.
210302| Conversion related settings in Auto bidding.  | Auto bidding for conversion is specified.
210303| Invalid conversion tracking.  | Conversion tracking is Invalid.
210304| Not enough conversions.  | Conversions is not enough.
210305| Auto bidding is already set.  | Auto bidding of "Enhanced CPC" or "Target conversion spend" is set for campaigns with individual bidding prices and bidding settings specified for keywords.
210306| Cannot use conversion optimizer.| Conversion optimizer cannot be used.
210307| Budget is lower than ad group/keywords.| The budget should be set higher than the budget set for the ad group / keyword in the campaign.
210308| Set campaign active.| Since the campaign is not ACTIVE, the bidding settings can not be used.
210309| Set campaign to Manual CPC.  | Since the campaign is not "Manual CPC", bidding settings can not be used.
210310| Select the correct bid type.  | It does not match the correct bid type.
210311| Campaign has been started.  | The start date of a campaign that has already started can not change.
210314| Cannot set Enhanced CPC for Mobile app download. | "Enhanced CPC" can not be set for Mobile app download.
210400| Double setting in Auto bidding.| BiddingStrategyType and biddingStrategyId are both specified.
210405| Budget has exceeded.  | The budget amount is exceeded.
210409| Bid setting limit has exceed.  | The bid amount or Auto bidding number set for the ad / ad group under the campaign exceeds the maximum limit. <br> * 1 The maximum bid amount and Auto bidding setting that can be set for the campaign is 1000 in total for the ad group below.
210504| Invalid settings in Auto bidding of campaign.  | "Enhanced CPC" or "Target conversion spend" is set in the campaign Auto bidding.
210505| Invalid settings in Auto bidding of ad group.  | "Enhanced CPC" or "Target conversion spend" is set in the ad group Auto bidding.
210509| Cannot set bidding keyword to negative keywords, or vice versa. | The keywords registered as negative keywords can not be registered as bidding keywords. The reverse is also true.
210510| Exists same text with match type. | The specified keyword, match type already exists in the campaign / ad group.
210517| Exceeds maximum word limit. | 10 keywords can only be specified up to.
210601| Multiple feeds are set in one ad. | Multiple feeds are set in one ad.
210605| App ad does not support Data Auto Insertion. | App ad does not support Data Auto Insertion.
210606| Cannot create double text ad. | It is not an account that can set double text ad.
211000| Cannot operate AdvancedURL.| Since it has already been transferred to AdvancedURL, it can not be operated.
211001| Cannot set AdvancedMobileURL. | In the app download campaign, AdvancedMobileURL can not be set.
211003| Domain does not match with DisplayURL.  | Domain of DisplayURL and AdvancedUrl do not match.
211004| Cannot set under AndroidCampaign.  | In the Android app campaign, the following settings can not be made：<br>・Set TrackingUrl and CustomParameter for campaigns, ad groups, ads, keywords<br>・Set the AdvancedUrl and AdvancedMobileUrl for the keywords
211005 | SharedList is used. | Negative keyword to be removed has been made setup to campaign.<br>(Negative keyword list setup to campaign cannot be removed.)
211006| Cannot bid modify criterion campaign opted out. | The bid adjustment rate for this device in an ad group because the device bid adjustment rate in the campaign have already been set to 0 (not delivered to that device) can not changed.
211007| Representative URL Does Not Match. | It is different from the domain set by FeedFolder.
211008| Cannot change Dynamic Ads for Search Campaign. | It can not be changed to the campaign of Dynamic Ads for Search.
211009| Cannot Update. | Dynamic Ads for Search FeedFolder can not be updated (mutate [set]).
211010| Cannot set excluded. | For AdGroupWebpageService, ExcludedType: EXCLUDED can not be set when WebpageConditionType: ALL_PAGES. In case of CampaignWebpageService, WebpageConditionType: ALL_PAGES can not be set.
211011| Cannot set DisplayURL and AdvancedURL,AdvancedMobileURL. | AdvancedUrl, AdvancedMobileUrl, DisplayUrl can not be set for Dynamic Ads for Search.
211012| Cannot update excluded type target. | Exclusion type target cannot be updated.
211014| Cannot remove FeedFolder related with campaign. | FeedFolder that is set for the campaign of Dynamic Ads for Search can not be deleted.
211015| Same feedFolderId UploadJob is in progress. | Since upload job of same feedFolderId is running, uploading is not possible.
211017| Cannot add Dynamic Search Ads Feed by Adult Account. | For the Adult Accounts, Feeds for Dynamic Ads for Search can not be registered.
225301| Cannot attach criteria at campaign and adgroup. | Target lists can not be associated with both ad groups and campaigns.
225302| Cannot add closed target list. | A closed target list can not be associated.
225305| invalid structured snippet header. | Structured snippet header is invalid.
225306| duplicate structured snippet values. | Structured snippet values is duplicated.

#### Reporting error
##### Service
[ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md),<br>
[ReportService](/docs/en/api_reference/services/ReportService.md)

 Code    | Message        | Description
-------- | -------------- | ------------------------
240002 | Invalid sortFields Item. | It contains combination items that cannot specify sortFields.
240003 | Invalid Filters Item. | It contains an item that cannot specify Filters.
240004 | Can not Specify Date Range.| Date range cannot be specified when the date range type is not CUSTOM_DATE.
240007 | Is Not Template.	| When the report template specification is FALSE, the timing of report creation can not be specified except for ONETIME.
240008 | Interval Type Is Not SPECIFY_DAY. | Cannot specify the report creation day when the timing of report creation is set other than SPECIFY_DAY.
