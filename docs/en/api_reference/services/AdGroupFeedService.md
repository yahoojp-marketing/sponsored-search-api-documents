# AdGroupFeedService
AdGroupFeedService is to get, add, update or remove the FeedItem information of ad groups.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Overview
Use this service to get, add, update or remove the FeedItem information of ad groups.
#### Operation
Describes the operation which provides by AdGroupFeedService.
## get
Returns FeedItem information of ad groups.
### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [AdGroupFeedSelector](../data/AdGroupFeedSelector.md) | The FeedItem selector for operaions. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:campaignIds>100000001</ns1:campaignIds>
                <ns1:campaignIds>100000002</ns1:campaignIds>
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:adGroupIds>100000012</ns1:adGroupIds>
                <ns1:adGroupIds>100000013</ns1:adGroupIds>
                <ns1:feedItemIds>12</ns1:feedItemIds>
                <ns1:feedItemIds>13</ns1:feedItemIds>
                <ns1:placeholderTypes>QUICKLINK</ns1:placeholderTypes>
                <ns1:placeholderTypes>CALLEXTENSION</ns1:placeholderTypes>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:campaignIds>100000001</ns1:campaignIds>
                <ns1:campaignIds>100000002</ns1:campaignIds>
                <ns1:adGroupIds>100000012</ns1:adGroupIds>
                <ns1:adGroupIds>100000018</ns1:adGroupIds>
                <ns1:feedItemIds>117</ns1:feedItemIds>
                <ns1:feedItemIds>123</ns1:feedItemIds>
                <ns1:feedItemIds>125</ns1:feedItemIds>
                <ns1:placeholderTypes>QUICKLINK</ns1:placeholderTypes>
                <ns1:placeholderTypes>CALLEXTENSION</ns1:placeholderTypes>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Filed | Data Type | Description | 
|---|---|---|
| rval | [AdGroupFeedPage](../data/AdGroupFeedPage.md) | This object is a container for selected FeedItem information.<br>Cannot retrieve the ad group without FeedItem information. | 

##### Response Sample
```xml
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupFeedService</ns1:service>
         <ns1:remainingQuota>2999</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>3.5343</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>AdGroupFeedPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupFeedList>
                   <ns1:accountId>1000000001</ns1:accountId>
                   <ns1:campaignId>1000000001</ns1:campaignId>
                   <ns1:adGroupId>1000000012</ns1:adGroupId>
                   <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   <ns1:adGroupFeed>
                       <ns1:accountId>1000000001</ns1:accountId>
                       <ns1:campaignId>1000000001</ns1:campaignId>
                       <ns1:adGroupId>1000000012</ns1:adGroupId>
                       <ns1:feedItemId>123</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:adGroupFeed>
                   <ns1:adGroupFeed>
                       <ns1:accountId>1000000001</ns1:accountId>
                       <ns1:campaignId>1000000001</ns1:campaignId>
                       <ns1:adGroupId>1000000012</ns1:adGroupId>
                       <ns1:feedItemId>125</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:adGroupFeed>
                   <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
               </ns1:adGroupFeedList>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupFeedList>
                   <ns1:accountId>1000000001</ns1:accountId>
                   <ns1:campaignId>1000000001</ns1:campaignId>
                   <ns1:adGroupId>1000000012</ns1:adGroupId>
                   <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   <ns1:adGroupFeed>
                       <ns1:accountId>1000000001</ns1:accountId>
                       <ns1:campaignId>1000000001</ns1:campaignId>
                       <ns1:adGroupId>1000000012</ns1:adGroupId>
                       <ns1:feedItemId>117</ns1:feedItemId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   </ns1:adGroupFeed>
                   <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
               </ns1:adGroupFeedList>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(SET)
Add, update or release(remove) FeedItem information of ad group. <br>
Update will overwrite the old information, so have to include the additional information on every updates. <br>
To release FeedItem information, update with blank data.<br>
It is possible to set FeedItem information to ad groups in different campaigns by single request.<br>
FeedItem information that can be set for a single ad group is up to 20 for each QUICKLINKS, CALLEXTENSION.<br>
*As for CALLEXTENSION, We recommend setting only one phone number per ad group.<br>

### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupFeedOperation](../data/AdGroupFeedOperation.md) | Operation elements for FeedItem information of ad group.<br>FeedItem setting will be overwritten.<br>To release FeedItem information, update with blank data. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
<!-- Connect QUICKLINK to adGroupId = 100000113 --> 
               <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>123</ns1:feedItemId>
                    </ns1:adGroupFeed>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>125</ns1:feedItemId>
                    </ns1:adGroupFeed>
                     </ns1:operand>
<!-- Connect CALLEXTENSION to adGroupId = 100000113 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>117</ns1:feedItemId>
                    </ns1:adGroupFeed>
                </ns1:operand>
<!-- Disconnect all QUICKLINK from adGroupId = 100000118 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
<!-- Disconnect all CALLEXTENSION from adGroupId = 100000118 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   </ns1:operand>
<!-- In case of specifying DESKTOP for devicePlatform of adGroupId = 100000119 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000119</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- In case of specifying SMART_PHONE for devicePlatform of adGroupId = 100000120 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000120</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- In case of specifying NONE for devicePlatform of adGroupId = 100000121 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000121</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>NONE</ns1:devicePlatform>
                </ns1:operand> 
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
<!-- Connect QUICKLINK to adGroupId = 100000113 --> 
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>123</ns1:feedItemId>
                    </ns1:adGroupFeed>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>125</ns1:feedItemId>
                    </ns1:adGroupFeed>
                     </ns1:operand>
<!-- Connect CALLEXTENSION to adGroupId = 100000113 --> 
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>117</ns1:feedItemId>
                    </ns1:adGroupFeed>
                </ns1:operand>
<!-- Disconnect all QUICKLINK from adGroupId = 100000118 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                             </ns1:operand>
<!-- Disconnect all CALLEXTENSION from adGroupId = 100000118 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
<!-- In case of specifying DESKTOP for devicePlatform of adGroupId = 100000119 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000119</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- In case of specifying SMART_PHONE for devicePlatform of adGroupId = 100000120 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000120</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- In case of specifying NONE for devicePlatform of adGroupId = 100000121 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000121</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>NONE</ns1:devicePlatform>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupFeedReturnValue](../data/AdGroupFeedReturnValue.md) | This object is a container for FeeItem information set on ad group which includes operation results. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:adGroupId>1000000012</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>1000000001</ns1:accountId>
                            <ns1:campaignId>1000000001</ns1:campaignId>
                            <ns1:adGroupId>1000000012</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                       </ns1:adGroupFeed>
                        <ns1:adGroupFeed>
                            <ns1:accountId>1000000001</ns1:accountId>
                            <ns1:campaignId>1000000001</ns1:campaignId>
                            <ns1:adGroupId>1000000012</ns1:adGroupId>
                            <ns1:feedItemId>125</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:adGroupId>1000000012</ns1:adGroupId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>1000000001</ns1:accountId>
                            <ns1:campaignId>1000000001</ns1:campaignId>
                            <ns1:adGroupId>1000000012</ns1:adGroupId>
                            <ns1:feedItemId>117</ns1:feedItemId>
                            <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        </ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- Response of deleting CALLEXTENSION by SET -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:adGroupId>1000000018</ns1:adGroupId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- Response of deleting QUICKLINK by SET -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:adGroupId>1000000018</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- Response of specifying DESKTOP for devicePlatform by SET -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:adGroupId>1000000019</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>1000000001</ns1:accountId>
                            <ns1:campaignId>1000000001</ns1:campaignId>
                            <ns1:adGroupId>1000000019</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed> 
                        <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- Response of specifying SMART_PHONE  for devicePlatform by SET -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:adGroupId>1000000020</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>1000000001</ns1:accountId>
                            <ns1:campaignId>1000000001</ns1:campaignId>
                            <ns1:adGroupId>1000000020</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed>
                        <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- Response of specifying NONE for devicePlatform by SET -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:adGroupId>1000000021</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>1000000001</ns1:accountId>
                            <ns1:campaignId>1000000001</ns1:campaignId>
                            <ns1:adGroupId>1000000021</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed>
                        <ns1:devicePlatform>NONE</ns1:devicePlatform>
                    </ns1:adGroupFeedList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
