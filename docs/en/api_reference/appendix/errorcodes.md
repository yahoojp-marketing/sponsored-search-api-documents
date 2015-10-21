# SOAP faults
List of SOAP error code and message when the error or problem occurs.  
### Overview
If your SOAP request is successful, the Sponsored Search API will return an HTTP 200 OK response code and the SOAP response.If an error occurs during the processing of your SOAP request, the Sponsored Search API will return an error code and message. See [Error](/docs/en/api_reference/data/Error.md) or [ErrorDetail](/docs/en/api_reference/data/ErrorDetail.md)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:error>
                <ns1:code>0011</ns1:code>
                <ns1:message>not login for apiAccountId</ns1:message>
                     <ns1:detail>
                         <ns1:requestKey>apiAccountId</ns1:requestKey>
                         <ns1:requestValue>aaaaaaaaaaa</ns1:requestValue>
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
Common  

Code | Message | Description  
---- | ------- | --------------  
0001 | Invalid Request.  | This error can result for a variety of reasons, typically because one of the parameter values in the request is wrong or invalid and the operation cannot be completed.  
0002 | An internal error has occurred.  | An internal error has occurred. Please try again later. If the problem persists please contact Yahoo! Japan API team for assistance. Be sure to include your SOAP Request and Response with your report.  
0003 | Frequency limit exceeded. Please try your request again later | Frequency limit exceeded. Please try your request again later.  
0004 | Invalid location.  | Account cannot be accessed at this location.  Please use the LocationService to retrieve the URL prefix for the colocation the account is assigned to.  
0005 | Quota exceeded. service = %s , Quota = %s | You have exceeded the daily operation quota for this web service. The daily quota is reset at midnight in JST.  
0006 | required | The soap header is missing required parameter.  
0007 | invalid number format | The number value is incorrect for this parameter.  
0008 | invalid string format | The string value is incorrect for this parameter.  
0009 | invalid enum | Your request contains an enumeration type value that is not valid.  
0010 | not a valid id | You have submitted an invalid ID. One of the ID indicated in the request was not found. This error may also result if onBehalfOfAccountId is not associated with the accountId which is in your request. Check the ID.  
0011 | not login for apiAccountId | The given apiAccountId could not log in. This could happen because of an incorrect apiAccountPassword or does not match the license in the request header.  
0011 | not login for onBehalfOfAccountId | The given OnBehalfOfAccountId could not log in. This could happen because of an incorrect OnBehalfOfPassword or does not match the accountId in the request header.  
0012 | status is invalid | The accountId or onBehalfOfAccountId indicated in the request is not active.  
0013 | method is invalid | The operation is not available. This error may also result if you specified a operation which does not exist. Check the operator.
0014 | selector is invalid.  | The selector is invalid. This error  result if you specified multiple selector in your request body. Check the operator.
0015 | operations is invalid.  | The operation is invalid. This error result if you specified multiple operation in your request body. Check the operator.
0016 | operator is invalid | This service does not support mutate operation.
0017 | over list size.  | Number of elements exceed maximum allowed in this object. Please reduce the size of your list based request and submit it again.
0018 | The data size you requested is too large. Please try your request again with a smaller date range or reduce the size of your request.  | The request failed because the requested size was too large. Adjust the data range or parameter and retry the request again.
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
0061 | Out of range.  | The setting is out from the limited range
0062 | Invalid relation.	| The relations is not valid.
0063 | Over limit.  | The setting is over the limit.
0064 | Invalid URL format.  | URL that been set is not valid.
0065 | Invalid step value.  | The step value is not valid.
0066 | Date set before the available period.  | Date has been set before the possible date range.
0067 | Date set after the available period.  | Date has been set after the possible date range.
0099 | Out of service.  | It is under maintenance. API cannot be used.


#### Account Management error
##### [AccountService](/docs/en/api_reference/services/AccountService.md)
Code  | Message  | Description 
----- | -------- | ---------------------------------
20110005 | INVALID VALUE | You have submitted invalid account IDs.  
20110006 | TOO MANY VALUE | Account IDs exceed maximum allowed.  
20110007 | INVALID VALUE CONTENT | You have submitted invalid account IDs. One of the account ID indicated in the request is not valid.  
20110011 | INVALID VALUE | You have submitted an invalid account statuses.  
20110012 | TOO MANY VALUE | Account statuses exceed maximum allowed.  
20110013 | INVALID VALUE CONTENT | You have submitted an invalid account statuses. One of the account status indicated in the request is not valid.  
20130008 | INVALID VALUE | You have submitted an invalid account.  
20130009 | INPUT REQUIRED | Account is required.  
20130010 | TOO MANY VALUE | Accounts exceed maximum allowed.  
20130011 | INVALID VALUE | You have submitted an invalid account ID.  
20130012 | INPUT REQUIRED | Account ID is required.  
20130013 | DUPLICATE VALUE | You have specified a duplicate account ID.  
20130014 | NO ACCOUNT FOUND | Account ID indicated in the request was not found.  
20130015 | CANNOT SET TO ACCOUNT | You cannot perform write operations for this accout.  
20130019 | INVALID VALUE | Account name specified in the request is not a valid account name.  
20130020 | CANNOT SET EMPTY | Account name specified in the request is empty. It should be not empty.  
20130021 | TOO LONG VALUE | Account name is too long.
20130022 | READ ONLY | Account Type is read-only.
20130027 | INVALID VALUE | Delivery status specified in the request is not a valid delivery status.
20130028 | CANNOT SET VALUE | You can not specify delivery status.
20410003 | INPUT REQUIRED | Account ID is required.
20410004 | INVALID VALUE | You have submitted an invalid account ID
20410005 | TOO MANY VALUE | Account IDs exceed maximum allowed. 
20410006 | INVALID VALUE CONTENT | You have submitted invalid account IDs. One of the account ID indicated in the request is not valid.
20410007 | NO ACCOUNT FOUND | One of the account IDs indicated in the request was not found. Check your account IDs.
20410008 | CANNOT GET BALANCE ACCOUNT | This operation is not applicable for account which choose payment type is invoice.
20410009 | GET BALANCE FAILED | The operation failed to get account balance.


#### Billing error
##### Service
##### [BalanceService](/docs/en/api_reference/services/BalanceService.md)  
 Code    | Message        | Description              
-------- | -------------- | ------------------------  
20410003 | INPUT REQUIRED | Account ID is required.
20410004 | INVALID VALUE | You have submitted an invalid account ID. 
20410005 | TOO MANY VALUE | Account IDs exceed maximum allowed. 
20410006 | INVALID VALUE CONTENT | You have submitted invalid account IDs. One of the account ID indicated in the request is not valid.
20410007 | NO ACCOUNT FOUND | One of the account IDs indicated in the request was not found. Check your account IDs
20410008 | CANNOT GET BALANCE ACCOUNT | This operation is not applicable for account which choose payment type is invoice.
20410009 | GET BALANCE FAILED | The operation failed to get account balance.


#### Campaign Management error
##### [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md),  [BulkService](/docs/en/api_reference/services/BulkService.md), [CampaignCriterionService](/docs/en/api_reference/services/CampaignCriterionService.md),  [CampaignTargetService](/docs/en/api_reference/services/CampaignTargetService.md), [CustomerSyncService](/docs/en/api_reference/services/CustomerSyncService.md), [AdGroupBidMultiplierService](/docs/en/api_reference/services/AdGroupBidMultiplierService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
0018 | The data size you requested is too large. Please try your request again with a smaller date range or reduce the size of your request.  | Failed operations due to data size excess.
10100 | DEACTIVATED | The entity is having status as deleted. This error may also result if account status is not active or the entity does not exist.
10200 | INVALID_STATUS | To update destinationUrl at keyword BiddableAdGroupCriterion, approbalStatus of the keyword must be "APPROVED"
10300 | OVER_LIMIT | Number of entities exceed maximum allowed. Please reduce the size of your request and submit it again.
10400 | EXISTS_SAME_NAME | The name you specified for a campaign, ad group, ad was not unique. Please choose one that is unique.
10501 | UNMATCH_BIDDING_STRATEGY_TYPE | Accelerated delivery method is not supported for budget optimizer. This error may also result if biddingStrategyType does not match campaign's biddingStrategyType.
10601 | OVER_BUDGET_AMOUNT | You cannot set/add amount greater than the amount specified for the campaign budget.
10602 | LOWER_BUDGET_AMOUNT | Have to set/add amount greater than the budget set for ad group or keywords of specific campaign.
10701 | EXISTS_DIFFERENT_CRITERION_USE_TYPE | The BiddableAdGroupCriterion already exists for NegativeAdGroupCriterion and vice versa.
10702 | EXISTS_SAME_TERM_WITH_MATCH_TYPE | The name you specified for a keyword with match type already exists in the campaign/ad group, cannot be duplicated.
10900 | UNMATCH_PLATFORM_TYPE | Invalid platformType.
10901 | UNMATCH_DEVICE_PREFERENCE | Invalid device preference setting. It is only valid in Unified Campaign.
20101 | REQUIRED | The operation is missing a required field or parameter or the value is empty.
20102 | NOT_LIST | The operation requires array.
20103 | OVER_LIST_SIZE | Number of elements exceed maximum allowed. Please reduce the size of your request and submit it again.
20104 | LOWER_LIST_SIZE | Specified list/container must not contain any null elements You must provide at least one valid object in this operation
20105 | NOT_HASH | The operation requires associative array (hash).
20401 | DUPLICATE | An element of added entity is duplicated with existing entity.
20601 | INVALID_NUMBER_FORMAT | The number value is incorrect for this parameter.
20602 | LOWER_NUMBER | A money amount was greater than the minimum allowed.
20603 | OVER_NUMBER | A money amount was greater than the maximum allowed.
20604 | INVALID_STEP_NUMBER | Invalid increments for budget amount.
20701 | INVALID_STRING_FORMAT | The string value is incorrect for this parameter.
20702 | LOWER_STRING | The string has too few characters.
20703 | OVER_STRING | The string has too many characters.
20901 | INVALID_DATE_FORMAT | The date value is incorrect for this parameter. The string date's format should be yyyymmdd.
20902 | LOWER_DATE | Date is before the date range.
20903 | OVER_DATE | Date is after the date range.
21001 | INVALID_ENUM | Your request contains an enumeration type value that is not valid.
21301 | INVALID_TARGET | Specified target type cannot be set to the campaign.
21401 | INVAILD_RELATION | The IDs or cliterionUse you provided is not valid. <br>This error may also result if you have specified an enddate which is earlier than the start date.                             
21601 | INVALID_URL_FORMAT | The url or destinationUrl in your request appears to be malformed or incomplete. Please check it.
120001 | REQUIRED | Request does not exist.  
120003 | INVALID NUMBER FORMAT | The number format is invalid.  
120016 | TOO LARGE VALUE | The number is larger.  
120017 | TOO SMALL VALUE | The number is small.  
120018 | DUPLICATE VALUE | The same Ad Group ID in the array.  
120022 | DEACTIVATED | Data does not exist.  
120027 | OVER LIST SIZE | Array is two or more.  
210605 | App ad does not support Data Auto Insertion. | Data Auto Insertion has been selected for App ad support.

##### Service
[CampaignService](/docs/ja/api_reference/services/CampaignService.md)  

Code                     | Message  | Description 
------ | ------------------------------------------ | -------------------------------------------------------
210300 | Double or no settings in Auto bidding.  | Bid type or Auto Bidding ID is not set, or both Bid type and Auto Bidding ID are set.
210301 | Setting the disabled Auto bidding.  | Designating the Auto bidding that in updating or deleted mode.
210302 | Conversion related settings in Auto bidding.  | Designating the Auto bidding that is related to conversion.
210303 | Invalid conversion tracking.  | Conversion tracking is not valid.
210304 | Not enough conversions.  | Conversion performance is not enough.
210305 | Auto bidding is already set.  | Setting the Auto Bidding of "Target CPC" or "Maximize conversions" to campaign, when Bid settings are made to keywords.
210306 | Cannot use conversion optimizer.  | Conversion optimizer is not available.
210307 | Budget is lower than ad group/keywords.	| Set the budget higher than the budget set in Ad Group and/or Keyword.
210308 | Set campaign active.	| Cannot set Auto Bidding when Campaign is not "ACTIVE".
210309 | Set campaign to Manual CPC.  | Cannot set Auto Bidding when Campaign is not "MANUAL_CPC".
210310 | Select the correct bid type.  | Bid type does not match.
210403 | Not enough conversions or invalid setting. |Conversion is not enough.<br>Conversion related bidding strategy has been set in Mobile app download campaign for iOS.


##### Service
[AdGroupService](/docs/en/api_reference/services/AdGroupService.md)  

Code   | Message  | Description 
------ | ----------------------------------- | ------------------------------------------------------------------
210400 | Double setting in Auto bidding.  | Cannot set both Bidding type and Auto bidding ID.  
210401 | Setting the disabled Auto bidding.  | Designating the Auto bidding that in updating or deleted mode.
210402 | Invalid conversion tracking.  | Conversion tracking is not valid.
210403 | Not enough conversions or invalid setting. |Conversion is not enough.<br>Conversion related bidding strategy has been set in Mobile app download campaign for iOS.
210404 | Auto bidding is already set.  | Setting the Auto Bidding of "Target CPC" or "Maximize conversions" to campaign, when Bid settings are made to keywords.
210405 | Budget has exceeded.  | Please change the budget to avoid exceeding the limit.
210406 | Cannot use conversion optimizer.  | Conversion optimizer is not available.
210407 | Set campaign active.	| Cannot set Auto Bidding when Campaign is not "ACTIVE".
210408 | Set campaign to Manual CPC.  | Cannot set Auto Bidding when Campaign is not "MANUAL_CPC".
210409 | Bid setting limit has exceed.  | It has exceeded the bid limit for Ad Group.

##### Service
[AdGroupCriterionService](/docs/en/api_reference/services/AdGroupCriterionService.md) 

Code   | Message  | Description 
------ | ----------------------------------------------------------------- | ------------------------------------------------------------------
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

##### Service
[BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md) 

Code   | Message  | Description 
------ | -------------------------------------------- | -------------------------------------------------------
210200 | Auto bidding has been used.  | Cannot delete because Auto Bidding is set to either Campaign, Ad Group, or Keyword.  
210201 | Minimum value is higher than maximum value.  | Click minimum value is set higher value than maximum value.
210202 | Auto bidding type does not match.  | Registered Auto Bidding type and requested Auto Bidding type does not match.

#### Reporting error
##### Service
[ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)

 Code    | Message        | Description              
-------- | ---------------------------- | ------------------------  
0002 | An internal error has occurred.  | An internal error has occurred. Please try again later. If the problem persists please contact Yahoo! JAPAN API team for assistance. Be sure to include your SOAP Request and Response with your report.
30001 | TEMPLATE_OVER | The error occurs when you create 31st report definitions. The limitation of report definitions you can store is 30. Please check and remove old report definitions.
30101 | JOB_OVER_ONETIME | The error occurs when you create 51st ONE TIME report job.<br>The limitation of ONE TIME report job ID you can store is 50.<br>Please check and remove old report job.
40001 | REQUIRED | The operation is missing a required field or parameter or the value is empty.
40002 | NOT_LIST | The operation requires array.
40003 | OVER_LIST_SIZE | Number of elements exceed maximum allowed. Please reduce the size of your request and submit it again.
40004 | LOWER_LIST_SIZE | Specified list/container must not contain any null elements. <br>You must provide at least one valid object in this operation
40011 | INVALID_NUMBER_FORMAT | The number value is incorrect for this parameter.  
40012 | LOWER_NUMBER | The number is too small.
40013 | OVER_NUMBER | The number is too big.
40021 | INVALID_STRING_FORMAT | The string value is incorrect for this parameter.
40022 | LOWER_STRING | The string has too few characters.
40023 | OVER_STRING | The string has too many characters.
40024 | INVALID_URL_FORMAT | The url or destinationUrl in your request appears to be malformed or incomplete. Please check it.
40026 | ILLEGAL_CHARACTER | The name element for this object contains one or more illegal characters.
40031 | INVALID_DATE_FORMAT | Date is before allowed minimum.Date is after allowed maximum.
40032 | OVER_DATE_RANGE | Date is outside of allowed range.
40041 | INVALID_ENUM | Your request contains an enumeration type value that is not valid.
40051 | INVALID_RELATION | This fault usually occurs when you have specified an enddate which is earlier than the start date.
40100 | JOB_IN_PROGRESS | Report delete procedure is made during report creation.
60003 | DATA_NOT_FOUND | The error occurs when the report ID you specified does not exixt.
60004 | JOB_IN_PROGRESS | The error occurs when you deleted report definitions of the active report job.

##### Service
[ReportService](/docs/en/api_reference/services/ReportService.md)

Code    | Message        | Description              
-------- | -------------------------------- | ------------------------  
0002 | An internal error has occurred.  | An internal error has occurred. Please try again later. If the problem persists please contact Yahoo! Japan API team for assistance. Be sure to include your SOAP Request and Response with your report.
40001 | REQUIRED | The operation is missing a required field or parameter or the value is empty.
40002 | NOT_LIST | The operation requires array.
40003 | OVER_LIST_SIZE | Number of elements exceed maximum allowed. Please reduce the size of your request and submit it again.
40004 | LOWER_LIST_SIZE | Specified list/container must not contain any null elements You must provide at least one valid object in this operation
40011 | INVALID_NUMBER_FORMAT | The number value is incorrect for this parameter.
40012 | LOWER_NUMBER | The number is too small.
40013 | LOWER_NUMBER | The number is too small.
40013 | OVER_NUMBER | The number is too big.

#### Forecasting error
##### Service
[BidLandscapeService](/docs/en/api_reference/services/BidLandscapeService.md), [TargetingIdeaService](/docs/en/api_reference/services/TargetingIdeaService.md),[TrafficEstimatorService](/docs/en/api_reference/services/TrafficEstimatorService.md),[KeywordEstimatorService](/docs/en/api_reference/services/KeywordEstimatorService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
20002 | INVALID VALUE | You have submitted an invalid account.
20003 | TOO HIGH | The number is too big.
20004 | TOO LOW | The number is too small.
30002 | INVALID VALUE | Parameter is invalid. Please make sure the parameter is not duplicated, lost or empty.
40002 | INVALID VALUE | Parameter is invalid.
40003 | TO LONG | The keyword has too many characters.
40004 | INVALID ENUM | Your request contains an enumeration type value that is not valid.
50002 | MISSING REQUIRED FIELED | Parameter specified in the request is lost or empty.
50004 | SIIZE LIMIT OVER | Number of elements exceed maximum allowed in this request.
80001 | DUPULICATED VALUE | You specified duplicated value.
80003 | ADGROUP NOT FOUND | AdGroup in the request was not found.
80004 | CRITERION NOT FOUND | Keyword in the request was not found.
80006 | TOO MANY WORDS | Number of keyword token exceed maximum allowed in this request.
80007 | INSUFFICIENT SEARCH PARAMETERS | No search term or URL is specified. When you specify EXCLUDED_KEYWORD you need to specify RELATED_TO_KEYWORD or RELATED_TO_URL.
120026 | REQUIRED BIDDABLE KEYWORD | Biddable keyword is required. 


#### ConversionTracker management error
##### Service
[ConversionTrackerService](/docs/en/api_reference/services/ConversionTrackerService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
120001 | REQUIRED | Required
120002 | INVALID VALUE | Value is invalid
120010 | TOO MANY ITEM | Item is too many
120012 | TOO MANY VALUE | Value is too many
120014 | TOO LONG VALUE | Value is too long
120016 | TOO LARGE VALUE | Value is too large
120017 | TOO SMALL VALUE | Value is too small.
120018 | DUPLICATE VALUE | Value is duplicated.
120022 | DEACTIVATED | Not active
120023 | OVER LIMIT | Limit is over
120024 | INVALID RELATION | Relation is invalid
210004 | INVALID SNIPPET FORMAT | Snipet format is invalid.


#### Feed Item error
##### Service
[FeedItemService](/docs/en/api_reference/services/FeedItemService.md)

 Code    | Message        | Description              
-------- | -------------- | ------------------------  
210101 | INVALID URL FORMAT | URL format in LINK_URL from FeedItemService is invalid. This error occur when adding the FeedItem information on QUICKLINK.  
210102 | INVALID PHONE NUMBER | Phone number in CALL_PHONE_NUMBER from FeedItemService is invalid. This error occur when adding the FeedItem information on CALLEXTENSION.  
210103 | UNMATCH PLACEHOLDER TYPE | Combination of placeholderType and feedItemId is not correct. For example, defining CALLEXTENSION in feedItemId for QUICKLINK in placeholderType in CampaignFeedSerivce or AdGroupFeedService.  
210104 | INVALID STATUS | Making SET in FeedAttributeValue during the APPROVED_WITH_REVIEW or REVIEW status in FeedItemService.
210105 | INVALID DATE FORMAT | Date format is invalid.
210106 | LOWER DATE | Date is too short.
210107 | OVER DATE | Date is too long.
210108 | LOWER NUMBER | Number is too small.
210109 | OVER NUMBER | Number is too big.
210110 | INVALID TARGET | Targeting is invalid.
210111 | Same value has already been registered | Please select different value to register.
210112 | can not delete a PlatformTarget | Were not able to delete the targeting.
210103 | can not modify a bidMultiplier | Were not able to change the bid multiplier.
210126 | Mobile app download cannot connect to Data Auto Insertion. |Connection to Data Auto Insertion has been attempted for Mobile app download.

##### Service
[CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md)

 Code    | Message        | Description   
------------------------ | ----------- | -------------------------------------------------------
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
------------------------ | ----------- | -------------------------------------------------------
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
210800 | Earlier than available date.| The date has been set earlier than the available date range
210801 | Later than available date.| The date has been set later than the available date range
210802 | Adult account selected.| Adult account cannot be selected.
210803 | Retargeting unavailable.| Account that retargeting been stopped from review.
210804 | Registered default list.| Cannot set the new default list to the account that has already set the default list.
210805 | Already used name.| Target list name is already registered.
210806 | Requires default list.| Cannot set condition list or combination list to the account that do not have default list registered.
210807 | Selecting Close default list.| ”CLOSE” has been selected to the selected default list.
210808 | Invalid rule operator.| Selecting the operator that cannot be selected.
210809 | Not logical target list.| Selecting combination target list to combination list.
210815 | Selecting only one target list.| Please select multiple target lists for combination list.
210816 | Selecting only Not condition.| Cannot select “NOT” condition only in combination list setting.


##### Service
[NegativeCampaignRetargetingListService](/docs/ja/api_reference/services/NegativeCampaignRetargetingListService.md)

 Code    | Message        | Description   
------------------------ | ----------- | -------------------------------------------------------
210810 | Status not approved.| Review is not approved for the selected target list.


##### Service
[AdGroupRetargetingListService](/docs/ja/api_reference/services/AdGroupRetargetingListService.md)

 Code    | Message        | Description   
------------------------ | ----------- | -------------------------------------------------------
210810 | Status not approved.| Review is not approved for the selected target list.
210811 | Target list not found.| Selected target list does not exist.
210812 | Already existing target list.| Selected target list is already registered.
210813 | Cannot bid the negative criterion.| Bidding setting been requested to the campaign or ad group that made exclude setting.
210814 | List already registered.| Combination of target or exclude list to the selected ad group ID is already registered.
