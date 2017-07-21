# SOAP faults
List of SOAP error code and message when the error or problem occurs.

### Overview
If your SOAP request is successful, the Sponsored Search API will return an HTTP 200 OK response code and the SOAP response. <br> If an error occurs during the processing of your SOAP request, Sponsored Search API will return an error code and message. <br>See [Error](/docs/en/api_reference/data/Error.md), [ErrorDetail](/docs/en/api_reference/data/ErrorDetail.md) for the entity details
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:error>
                <ns1:code>0011</ns1:code>
                <ns1:message>not login for apiAccountId</ns1:message>
                     <ns1:detail>
                         <ns1:requestKey>apiAccountId</ns1:requestKey>
                         <ns1:requestValue>xxxxxxxxxxxxxxxxx</ns1:requestValue>
                     </ns1:detail>
            </ns1:error>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Error Codes
Sponsored Search API returns these SOAP faults when errors occur.
#### Authentication error

##### Service
All services.

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
0001 | Invalid Request.  | This error can result for a variety of reasons. <br>Typically because one of the parameter values in the request is wrong or invalid and the operation cannot be completed.  
0002 | An internal error has occurred.  | An internal error has occurred. Please try again later. <br>If the problem continues, please contact the support team via Inquiry page for assistance. <br>*Be sure to have your SOAP Request/Response ready.
0003 | Frequency limit exceeded. Please try your request again later. | Frequency limit exceeded. Please try your request again later.  
0004 | Invalid location.  | Account cannot be accessed at this location. <br>Please use the LocationService to retrieve the URL prefix for the colocation the account is assigned to.  
0006 | required. | The soap header is missing required parameter.  
0007 | invalid number format. | The number value is incorrect for this parameter.  
0008 | invalid string format. | The string value is incorrect for this parameter.  
0009 | invalid enum. | Your request contains an enumeration type value that is not valid.  
0010 | not a valid id. | You have submitted an invalid ID. One of the ID indicated in the request was not found. <br>This error may also result if onBehalfOfAccountId is not associated with the accountId which is in your request.  
0011 | not login for apiAccountId. | The given apiAccountId could not log in. <br>This could happen because of an incorrect apiAccountPassword or does not match the license in the request header.  
0011 | not login for onBehalfOfAccountId. | The given OnBehalfOfAccountId could not log in. <br>This could happen because of an incorrect OnBehalfOfPassword or does not match the accountId in the request header.  
0012 | status is invalid. | The accountId or onBehalfOfAccountId indicated in the request is not active.  
0013 | method is invalid. | The operation is not available. <br>This error may also result if you specified a operation which does not exist.
0014 | selector is invalid.  | The selector is invalid. <br>This error result if you specified multiple selector in your request body.
0015 | operations is invalid.  | The operation is invalid. <br>This error result if you specified multiple operation in your request body.
0016 | operator is invalid | This service does not support mutate operation.
0017 | over list size.  | Number of elements exceed maximum allowed in this object. <br>Please reduce the size of your list based request and submit it again.
0018 | The data size you requested is too large. Please try your request again with a smaller date range or reduce the size of your request.  | The request failed because the requested size was too large. <br>Adjust the data range or parameter and retry the request again.
0050 | Too many items.  | Number of items are too many.
0051 | Too little items.  | Number of items are too little.
0052 | Too many values.  | The number of values are too many.
0053 | Too little values.  | The number of values are too little.
0054 | Too long values.  | The number of values are too long.
0055 | Too short value.  | The number of values are too short.
0056 | Too large value.  | The number is too large.
0057 | Too small value.  | The number is too small.
0058 | Duplicate values.  | The vlaues are duplicate.
0059 | Same value has already been registered.  | The same values are already set. Please set in different value.
0060 | Invalid date format.	| The date format is not valid.
0061 | Out of range.  | The setting is out from the limited range.
0062 | Invalid relation.	| The relations is not valid.
0063 | Over limit.  | The setting is over the limit.
0064 | Invalid url format.  | URL that been set is not valid.
0065 | Invalid step value.  | The step value is not valid.
0066 | Date set before the available period.  | Date has been set before the possible date range.
0067 | Date set after the available period.  | Date has been set after the possible date range.
0099 | Out of service.  | API is under maintenance or not available to use.

#### Account Management error
##### Service
[AccountService](/docs/en/api_reference/services/AccountService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
20110005 | INVALID VALUE | You have submitted invalid account IDs.  
20110006 | TOO MANY VALUE | Account IDs exceed maximum allowed.  
20110007 | INVALID VALUE CONTENT | You have submitted invalid account IDs. <br>One of the account ID indicated in the request is not valid.  
20110011 | INVALID VALUE | You have submitted an invalid account statuses.  
20110012 | TOO MANY VALUE | Account statuses exceed maximum allowed.  
20110013 | INVALID VALUE CONTENT | You have submitted an invalid account statuses. <br>One of the account status indicated in the request is not valid.  
20130008 | INVALID VALUE | You have submitted an invalid account.  
20130009 | INPUT REQUIRED | Account is required.  
20130010 | TOO MANY VALUE | Accounts exceed maximum allowed.  
20130011 | INVALID VALUE | You have submitted an invalid account ID.  
20130012 | INPUT REQUIRED | Account ID is required.  
20130013 | DUPLICATE VALUE | You have specified a duplicate account ID.  
20130014 | NO ACCOUNT FOUND | Account ID indicated in the request was not found.  
20130015 | CANNOT SET TO ACCOUNT | You cannot perform write operations for this accout.  
20130019 | INVALID VALUE | Account name specified in the request is not a valid account name.  
20130020 | CANNOT SET EMPTY | Account name specified in the request is empty.
20130021 | TOO LONG VALUE | Account name is too long.
20130022 | READ ONLY | Account Type is read-only.
20130027 | INVALID VALUE | Delivery status specified in the request is not a valid delivery status.
20130028 | CANNOT SET VALUE | You can not specify delivery status.
20410003 | INPUT REQUIRED | Account ID is required.
20410004 | INVALID VALUE | You have submitted an invalid account ID.
20410005 | TOO MANY VALUE | Account IDs exceed maximum allowed. 
20410006 | INVALID VALUE CONTENT | You have submitted invalid account IDs. <br>One of the account ID indicated in the request is not valid.
20410007 | NO ACCOUNT FOUND | One of the account IDs indicated in the request was not found. <br>Please confirm your account IDs.
20410009 | GET BALANCE FAILED | The operation failed to get account balance.

##### Service
[AccountTrackingUrlService](/docs/ja/api_reference/services/AccountTrackingUrlService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
210903 | Invalid role. | Account authorization is not valid.
210905 | Invalid status. | Cannot change the approval status when in review.
210907 | url restriction. | URL that cannot be submitted was set.
210909 | not account updatable. | Account is not in updatable condition.


#### Billing error
##### Service
[BalanceService](/docs/en/api_reference/services/BalanceService.md)  

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
20410003 | INPUT REQUIRED | Account ID is required.
20410004 | INVALID VALUE | You have submitted an invalid account ID. 
20410005 | TOO MANY VALUE | Account IDs exceed maximum allowed. 
20410006 | INVALID VALUE CONTENT | You have submitted invalid account IDs. <br>One of the account ID indicated in the request is not valid.
20410007 | NO ACCOUNT FOUND | One of the account IDs indicated in the request was not found. <br>Please confirm your account IDs
20410009 | GET BALANCE FAILED | The operation failed to get account balance.

#### Campaign Management error
##### Service
[AccountSharedService](/docs/en/api_reference/services/AccountSharedService.md), <br>
[AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md), <br> 
[AdGroupBidMultiplierService](/docs/en/api_reference/services/AdGroupBidMultiplierService.md), <br>
[CampaignExportService](/docs/en/api_reference/services/CampaignExportService.md), <br> [CampaignCriterionService](/docs/en/api_reference/services/CampaignCriterionService.md), <br> 
[CampaignSharedSetService](/docs/en/api_reference/services/CampaignSharedSetService.md), <br>
[CampaignTargetService](/docs/en/api_reference/services/CampaignTargetService.md), <br> [CustomerSyncService](/docs/en/api_reference/services/CustomerSyncService.md), <br> 
[SharedCriterionService](/docs/en/api_reference/services/SharedCriterionService.md), <br>


 Code    | Message        | Description              
-------- | -------------- | ------------------------  
0018 | The data size you requested is too large. <br>Please try your request again with a smaller date range or reduce the size of your request.  | Failed operations due to data size excess.
0102 | DEACTIVATED | There is no such account, account status is invalid, the account has been already deleted.
0103 | Exists same name. | The name you specified for a campaign, ad group, ad was not unique. <br>Please choose one that is unique.
1003 | invalid download request. | Host of creating and host of obtaining the Download URL differs.
1004 | download URL has expired. | Passed the retainment period of Download URL (10 minutes after report creation)<br />Download URL may have falsified.
10100 | DEACTIVATED | The entity is having status as deleted. <br>This error may also result if account status is not active or the entity does not exist.
10200 | INVALID_STATUS | To update destinationUrl at keyword BiddableAdGroupCriterion, approbalStatus of the keyword must be "APPROVED"
10300 | OVER_LIMIT | Number of entities exceed maximum allowed. <br>Please reduce the size of your request and submit it again.
10501 | UNMATCH_BIDDING _STRATEGY_TYPE | Accelerated delivery method is not supported for budget optimizer. <br>This error may also result if biddingStrategyType does not match campaign's biddingStrategyType.
10601 | OVER_BUDGET_AMOUNT | You cannot set/add amount greater than the amount specified for the campaign budget.
10602 | LOWER_BUDGET_AMOUNT | Have to set/add amount greater than the budget set for ad group or keywords of specific campaign.
10701 | EXISTS_DIFFERENT _CRITERION_USE_TYPE | The BiddableAdGroupCriterion already exists for NegativeAdGroupCriterion and vice versa.
10702 | EXISTS_SAME_TERM _WITH_MATCH_TYPE | The name you specified for a keyword with match type already exists in the campaign/ad group, cannot be duplicated.
10900 | UNMATCH_PLATFORM_TYPE | Invalid platformType.
10901 | UNMATCH_DEVICE _PREFERENCE | Invalid device preference setting. <br>It is only valid in Unified Campaign.
20101 | REQUIRED | The operation is missing a required field or parameter or the value is empty.
20102 | NOT_LIST | The operation requires array.
20103 | OVER_LIST_SIZE | Number of elements exceed maximum allowed. <br>Please reduce the size of your request and submit it again.
20104 | LOWER_LIST_SIZE | Specified list/container must not contain any null elements You must provide at least one valid object in this operation.
20105 | NOT_HASH | The operation requires associative array (hash).
20401 | DUPLICATE | An element of added entity is duplicated with existing entity.
20601 | INVALID_NUMBER_FORMAT | The number value is incorrect for this parameter.
20602 | LOWER_NUMBER | A money amount was greater than the minimum allowed.
20603 | OVER_NUMBER | A money amount was greater than the maximum allowed.
20604 | INVALID_STEP_NUMBER | Invalid increments for budget amount.
20701 | INVALID_STRING_FORMAT | The string value is incorrect for this parameter.
20702 | LOWER_STRING | The string has too few characters.
20703 | OVER_STRING | The string has too many characters.
20901 | INVALID_DATE_FORMAT | The date value is incorrect for this parameter. <br>The string date's format should be YYYYMMDD.
20902 | LOWER_DATE | Date is before the date range.
20903 | OVER_DATE | Date is after the date range.
21001 | INVALID_ENUM | Your request contains an enumeration type value that is not valid.
21301 | INVALID_TARGET | Specified target type cannot be set to the campaign.
21401 | INVAILD_RELATION | The IDs or cliterionUse you provided is not valid.  <br>This error may also result if you have specified an enddate which is earlier than the start date.                            
21601 | INVALID_URL_FORMAT | The url or destinationUrl in your request appears to be malformed or incomplete. <br>Please check it.
120001 | REQUIRED | Request does not exist.  
120003 | INVALID NUMBER FORMAT | The number format is invalid.  
120016 | TOO LARGE VALUE | The number is larger.  
120017 | TOO SMALL VALUE | The number is small.  
120018 | DUPLICATE VALUE | The same Ad Group ID in the array.  
120022 | DEACTIVATED | Data does not exist.  
120027 | OVER LIST SIZE | Array is two or more. 
211001 | Cannot set AdvancedMobileURL. | Cannot set advancedMobileUrl in Mobile app download.
211003 | Domain does not match with DisplayURL.  | Display URL and Landing Page URL (including mobile) domain does not match.
211004 | Cannot set under AndroidCampaign.  | Cannot set as below for App campaign for Android: <br>- Setting TrackingUrl and/or CustomParameter in Campaign, Ad Group, Ad, and Keyword.
211005 | SharedList is used. | Negative keyword to be removed has been made setup to campaign.<br>(Negative keyword list setup to campaign cannot be removed.)
211006 | Cannot bid modify criterion campaign opted out. | Because Bid Adjustment rate by device on campaign has been set as 100% already, the Bid Adjustment rate for same device on ad group cannot be edited.

##### Service
[CampaignService](/docs/ja/api_reference/services/CampaignService.md)  
  
 Code    | Message        | Description              
-------- | -------------- | ------------------------  
210300 | Double or no settings in Auto bidding.  | Bid type or Auto Bidding ID is not set, or both Bid type and Auto Bidding ID are set.
210301 | Setting the disabled Auto bidding.  | Designating the Auto bidding that in updating or deleted mode.
210302 | Conversion related settings in Auto bidding.  | Designating the Auto bidding that is related to conversion.
210303 | Invalid conversion tracking.  | Conversion tracking is not valid.
210304 | Not enough conversions.  | Conversion performance is not enough.
210305 | Auto bidding is already set.  | Setting the Auto Bidding of "Target CPC" or "Maximize conversions" to campaign, when Bid settings are made to keywords.
210306 | Cannot use conversion optimizer.  | Conversion Optimizer is not available.
210307 | Budget is lower than ad group/keywords.	| Set the budget higher than the budget set in Ad Group and/or Keyword.
210308 | Set campaign active.	| Cannot set Auto Bidding when Campaign is not "ACTIVE".
210309 | Set campaign to Manual CPC.  | Cannot set Auto Bidding when Campaign is not "MANUAL_CPC".
210310 | Select the correct bid type.  | Bid type does not match.
210311 | Campaign has been started.  | The start date of the campaign which has started cannot be changed. 
211000 | Cannot operate AdvancedURL.	| Cannot change because it has already migrated to Advanced URL. 
211001 | Cannot set AdvancedMobileURL. | Cannot set advancedMobileUrl in Mobile app download
211002 | Lpurl is required for ValueTrack.	| Include {lpurl} in Tracking URL.
211003 | Domain does not match with DisplayURL.  | Display URL and Landing Page URL (including mobile) domain does not match.
211004 | Cannot set under AndroidCampaign.  | Cannot set as below for App campaign for Android: <br> - Setting TrackingUrl and/or CustomParameter in Campaign, Ad Group, Ad, and Keyword.<br> - Setting Landing Page URL and/or URL for Smartphone in Keyword.

##### Service
[AdGroupService](/docs/en/api_reference/services/AdGroupService.md)  

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
210301 | Setting the disabled Auto bidding.  | Designating the Auto bidding that in updating or deleted mode.
210400 | Double setting in Auto bidding.  | Cannot set both Bidding type and Auto bidding ID.  
210402 | Invalid conversion tracking.  | Conversion tracking is not valid.
210403 | Not enough conversions.  | Conversion performance is not enough.
210404 | Auto bidding is already set.  | Setting the Auto Bidding of "Target CPC" or "Maximize conversions" to campaign, when Bid settings are made to keywords.
210405 | Budget has exceeded.  | Please change the budget to avoid exceeding the limit.
210406 | Cannot use conversion optimizer.  | Auto Bidding setting is not available.
210407 | Set campaign active.	| Cannot set Auto Bidding when Campaign is not "ACTIVE".
210408 | Set campaign to Manual CPC.  | Cannot set Auto Bidding when Campaign is not "MANUAL_CPC".
210409 | Bid setting limit has exceed.  | Number of bidding settings or number of Auto Bidding settings for the ad group under the campaign has exceeded the maximum limit. <br> *Up to 1000 settings are totally available for all ad groups under a single campaign.
211000 | Cannot operate AdvancedURL.	| Cannot change because it has already migrated to Advanced URL. 
211001 | Cannot set AdvancedMobileURL. | Cannot set advancedMobileUrl in Mobile app download.
211002 | Lpurl is required for ValueTrack.	| Include {lpurl} in Tracking URL.
211003 | Domain does not match with DisplayURL.  | Display URL and Landing Page URL (including mobile) domain does not match.
211004 | Cannot set under AndroidCampaign.  | Cannot set as below for App campaign for Android: <br> - Setting TrackingUrl and/or CustomParameter in Campaign, Ad Group, Ad, and Keyword.<br> - Setting Landing Page URL and/or URL for Smartphone in Keyword.

##### Service
[AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md) 

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
210500 | Double setting in Auto bidding.  | Cannot set both Bidding type and Auto bidding ID.  
210501 | Setting the disabled Auto bidding.  | Designating the Auto bidding that in updating or deleted mode.
210502 | Invalid conversion tracking.  | Conversion tracking is not valid.
210503 | Not enough conversions.  | Conversion performance is not enough.
210504 | Invalid settings in Auto bidding of campaign.  | Setting the Auto Bidding of "Target CPC" or "Maximize conversions" to Campaign.
210505 | Invalid settings in Auto bidding of ad group.  | Setting the Auto Bidding of "Target CPC" or "Maximize conversions" to Ad Group.
210506 | Invalid keyword settings.  | Designated keyword cannot be set for Auto bidding.
210507 | Budget has exceeded.  | Please change the budget to avoid exceeding the limit.
210508 | Keyword is not approved yet.  | In order to update the Custom URL, keywords have to be "APPROVED".
210509 | Cannot set bidding keyword to negative keywords, or vice versa.  | Cannot set as bid keyword that is already set as negative keywords. Same for vice versa.
210510 | Setting already exists in campaign/ad group.  | Designated keywords or match type is already exist in the Campaign or Ad Group.
210511 | Cannot use conversion optimizer.  | Conversion optimizer is not available.
210512 | Set campaign active.	| Cannot set Auto Bidding when Campaign is not "ACTIVE".
210513 | Set campaign to Manual CPC.  | Cannot set Auto Bidding when Campaign is not "MANUAL_CPC".
210517 | Exceeds maximum word limit. | Cannot set more than 10 keywords.
211000 | Cannot operate AdvancedURL.	| Cannot change because it has already migrated to Advanced URL. 
211001 | Cannot set AdvancedMobileURL. | Cannot set advancedMobileUrl in Mobile app download.
211004 | Cannot set under AndroidCampaign.  | Cannot set as below for App campaign for Android: <br> - Setting TrackingUrl and/or CustomParameter in Campaign, Ad Group, Ad, and Keyword.<br> - Setting Landing Page URL and/or URL for Smartphone in Keyword.

##### Service
[BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md) 

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
210200 | Auto bidding has been used.  | Cannot delete because Auto Bidding is set to either Campaign, Ad Group, or Keyword.  
210201 | Minimum value is higher than maximum value.  | Click minimum value is set higher value than maximum value.
210202 | Auto bidding type does not match.  | Registered Auto Bidding type and requested Auto Bidding type does not match.


#### Reporting error
##### Service
[ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
0002 | An internal error has occurred.  | An internal error has occurred. Please try again later. <br>If the problem continues, please contact the support team via Inquiry page for assistance. <br>*Be sure to have your SOAP Request/Response ready.
0108 | entity count limit exceeded.  | The error occurs when you create 31st report definitions.<br>The limitation of report definitions you can store is 30.<br>Please check and remove old report definitions.
20103 | OVER_LIST_SIZE| The element count exceeded the maximum.
40001 | REQUIRED | The operation is missing a required field or parameter or the value is empty.
40002 | NOT_LIST | The operation requires array.
40003 | OVER_LIST_SIZE | Number of elements exceed maximum allowed. <br>Please reduce the size of your request and submit it again.
40004 | LOWER_LIST_SIZE | Specified list/container must not contain any null elements. <br>You must provide at least one valid object in this operation
40011 | INVALID_NUMBER_FORMAT | The number value is incorrect for this parameter.  
40012 | LOWER_NUMBER | The number is too small.
40013 | OVER_NUMBER | The number is too big.
40021 | INVALID_STRING_FORMAT | The string value is incorrect for this parameter.
40022 | LOWER_STRING | The string has too few characters.
40023 | OVER_STRING | The string has too many characters.
40024 | INVALID_URL_FORMAT | The url or destinationUrl in your request appears to be malformed or incomplete. <br>Please check it.
40026 | ILLEGAL_CHARACTER | The name element for this object contains one or more illegal characters.
40031 | INVALID_DATE_FORMAT | Date is before allowed minimum. <br>Date is after allowed maximum.
40032 | OVER_DATE_RANGE | Date is outside of allowed range.
40041 | INVALID_ENUM | Your request contains an enumeration type value that is not valid.
40051 | INVALID_RELATION | This fault usually occurs when you have specified an enddate which is earlier than the start date.
40100 | JOB_IN_PROGRESS | Report delete procedure is made during report creation.
60003 | DATA_NOT_FOUND | The error occurs when the report ID you specified does not exixt.
60004 | JOB_IN_PROGRESS | The error occurs when you deleted report definitions of the active report job.
240000 | Contains Invalid Character. | It contains a character that oppose Insertion Rules.
240002 | Invalid sortFields Item. | It contains combination items that cannot specify sortFields.
240003 | Invalid Filters Item. | It contains an item that cannot specify Filters.
240004 | Can not Specify Date Range.| Date range cannot be specified when the date range type is not CUSTOM_DATE.
240007 | Is Not Template. | Cannot specify the timing of report creation other than ONETIME when the report template is FALSE.
240008 | Interval Type Is Not SPECIFY_DAY. | Cannot specify the report creation day when the timing of report creation is set other than SPECIFYDAY.


##### Service
[ReportService](/docs/en/api_reference/services/ReportService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------    
0002 | An internal error has occurred.  | An internal error has occurred. Please try again later. <br>If the problem continues, please contact the support team via Inquiry page for assistance. <br>*Be sure to have your SOAP Request/Response ready.
0108 | entity count limit exceeded.  | The error occurs when you create 51st ONE TIME report job.<br>The limitation of ONE TIME report job ID you can store is 50.<br>Please check and remove old report job.
20103 | OVER_LIST_SIZE| The element count exceeded the maximum.
40001 | REQUIRED | The operation is missing a required field or parameter or the value is empty.
40002 | NOT_LIST | The operation requires array.
40003 | OVER_LIST_SIZE | Number of elements exceed maximum allowed. <br>Please reduce the size of your request and submit it again.
40004 | LOWER_LIST_SIZE | Specified list/container must not contain any null elements. <br>You must provide at least one valid object in this operation.
40011 | INVALID_NUMBER_FORMAT | The number value is incorrect for this parameter.
40012 | LOWER_NUMBER | The number is too small.
40013 | OVER_NUMBER | The number is too big.

#### Forecasting error
##### Service
[BidLandscapeService](/docs/en/api_reference/services/BidLandscapeService.md), <br> [TargetingIdeaService](/docs/en/api_reference/services/TargetingIdeaService.md), 
<br>  [KeywordEstimatorService](/docs/en/api_reference/services/KeywordEstimatorService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------
20002 | INVALID VALUE | You have submitted an invalid account.
20003 | TOO HIGH | The number is too big.
20004 | TOO LOW | The number is too small.
30002 | INVALID VALUE | Parameter is invalid. <br>Please make sure the parameter is not duplicated, lost or empty.
40002 | INVALID VALUE | Parameter is invalid. <br>Please make sure the parameter is not duplicated, lost or empty.
40003 | TO LONG | The keyword has too many characters.
40004 | INVALID ENUM | Your request contains an enumeration type value that is not valid.
50002 | MISSING REQUIRED FIELED | Parameter specified in the request is lost or empty.
50004 | SIIZE LIMIT OVER | Number of elements exceed maximum allowed in this request.
80001 | DUPULICATED VALUE | You specified duplicated value.
80003 | ADGROUP NOT FOUND | AdGroup in the request was not found.
80004 | CRITERION NOT FOUND | Keyword in the request was not found.
80006 | TOO MANY WORDS | Number of keyword token exceed maximum allowed in this request.
80007 | INSUFFICIENT SEARCH PARAMETERS | No search term or URL is specified. <br>When you specify EXCLUDED_KEYWORD you need to specify RELATED_TO_KEYWORD or RELATED_TO_URL.
120026 | REQUIRED BIDDABLE KEYWORD | Biddable keyword is required. 

#### ConversionTracker management error
##### Service
[ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
120001 | REQUIRED | Required.
120002 | INVALID VALUE | Value is invalid.
120010 | TOO MANY ITEM | Item is too many.
120012 | TOO MANY VALUE | Value is too many.
120014 | TOO LONG VALUE | Value is too long.
120016 | TOO LARGE VALUE | Value is too large.
120017 | TOO SMALL VALUE | Value is too small.
120018 | DUPLICATE VALUE | Value is duplicated.
120022 | DEACTIVATED | Not active.
120023 | OVER LIMIT | Limit is over.
120024 | INVALID RELATION | Relation is invalid.
210004 | INVALID SNIPPET FORMAT | Snipet format is invalid.

#### Feed Item error
##### Service
[FeedItemService](/docs/en/api_reference/services/FeedItemService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------   
20103 | OVER_LIST_SIZE| The element count exceeded the maximum.
21601 | Invalid url format. | QuickLink URL and/or Custom URL of Keyword is not valid.
210102 | INVALID PHONE NUMBER | Phone number in CALL_PHONE_NUMBER from FeedItemService is invalid. <br>This error occur when adding the FeedItem information on CALLEXTENSION.  
210104 | INVALID STATUS | Since it is in review, cannot be updated.
210110 | INVALID TARGET | Number of scheduled targeting settings exceeds the maximum items per a day (max: 6).
211000 | Cannot operate AdvancedURL.	| Cannot change because it has already migrated to Advanced URL. 
210123 | CAMPAIGN TARGETING MISMATCH 	| It is not available to set, since the campaign ID specified with 'targetingCampaignId' does not match to the parent campaign ID of the ad group specified with 'targetingAdGroupId'.
210126 | Mobile app download cannot connect to. | Mobile App Download campaign is not available.

##### Service
[CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
20103 | OVER_LIST_SIZE| The element count exceeded the maximum.
120002 | INVALID VALUE| Value is invalid.
120018 | DUPLICATE VALUE| Value is overlapped. Please use different value.
120022 | DEACTIVATED| Invalid ID has been specified.
120024 | INVALID RELATION| Relation is invalid.
210103 | UNMATCH PLACEHOLDER TYPE| Inappropriate combination of placeholderType and feedItemId.
210127 | Mobile app download cannot connect to Feed item.|Connection to Feed item has been attempted for Mobile app download.

##### Service
[AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
20103 | OVER_LIST_SIZE| The element count exceeded the maximum.
120002 | INVALID VALUE| Value is invalid.
120018 | DUPLICATE VALUE| Value is overlapped. Please use different value.
120022 | DEACTIVATED| Invalid ID has been specified.
120024 | INVALID RELATION| Relation is invalid.
210103 | UNMATCH PLACEHOLDER TYPE| Inappropriate combination of placeholderType and feedItemId.
210127 | Mobile app download cannot connect to Feed item.|Connection to Feed item has been attempted for Mobile app download.

#### Retargeting Error
##### Service
[RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

 Code    | Message        | Description   
------------------------ | ----------- | -------------------------------------------------------
210802 | Adult account selected.| Adult account cannot be selected.
210803 | Retargeting unavailable.| Account that retargeting been stopped from review.
210804 | Registered default list.| Cannot set the new default list to the account that has already set the default list.
210806 | Requires default list.| Cannot set condition list or combination list to the account that do not have default list registered.
210807 | Selecting Close default list.| ”CLOSE” has been selected to the selected default list.
210808 | Invalid rule operator.| Selecting the operator that cannot be selected.
210809 | Not logical target list.| Selecting combination target list to combination list.
210815 | Selecting only one target list.| Please select multiple target lists for combination list.
210816 | Selecting only Not condition.| Cannot select “NOT” condition only in combination list setting.
210822 | Cannot create a share target list. | When no shared account setting, shared Target List cannot be added.

##### Service
[CampaignRetargetingListService](/docs/ja/api_reference/services/CampaignRetargetingListService.md)

 Code    | Message        | Description   
------------------------ | ----------- | -------------------------------------------------------
210810 | Status not approved. | Review is not approved for the selected target list.
210812 | Already existing target list. | 'Exclude/Include' setting of the Target List has been already made for the ad group ID. (For a single ad group, one target list for each Exclude and Include setting is available for setup.
210813 | Cannot bid the negative criterion. | Bid adjustment rate is set although the target list setting is as 'Exclude'.
225301 | Cannot attach criteria at campaign and adgroup. | Target list cannot be setup both for ad group and campaign.


##### Service
[AdGroupRetargetingListService](/docs/ja/api_reference/services/AdGroupRetargetingListService.md)

 Code    | Message        | Description   
------------------------ | ----------- | -------------------------------------------------------
210810 | Status not approved.| Review is not approved for the selected target list.
210811 | Target list not found.| Selected target list does not exist.
210812 | Already existing target list.| Selected target list is already registered.
210813 | Cannot bid the negative criterion.| Bidding setting been requested to the campaign or ad group that made exclude setting.
210814 | List already registered.| Combination of target or exclude list to the selected ad group ID is already registered.
225301 |  Cannot attach criteria at campaign and adgroup. | Target list cannot be setup both for ad group and campaign.
