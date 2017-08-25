# CampaignFeedService
CampaignFeedService is to get and update the FeedItem information of campaign.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/CampaignFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/CampaignFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Overview
Use this service to get, add, update or remove the FeedItem information of campaign.
#### Operation
Describes the operation which provides by CampaignFeedService.
## get
Get FeedItem information of campaign.
### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [CampaignFeedSelector](../data/CampaignFeedSelector.md) | The FeedItem selector for operaions. | 
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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:campaignIds>100000004</ns1:campaignIds>
                <ns1:feedItemIds>123</ns1:feedItemIds>
                <ns1:feedItemIds>124</ns1:feedItemIds>
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
| rval | [CampaignFeedPage](../data/CampaignFeedPage.md) | This object is a container for selected FeedItem information. | 

##### Response Sample
```xml
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignFeedService</ns1:service>
         <ns1:remainingQuota>2983</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>2.6619</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>CampaignFeedPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignFeedList>
                   <ns1:accountId>100000001</ns1:accountId>
                   <ns1:campaignId>100000003</ns1:campaignId>
                   <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   <ns1:campaignFeed>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:feedItemId>113</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:campaignFeed>
                   <ns1:campaignFeed>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:feedItemId>114</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:campaignFeed>
                   <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
               </ns1:campaignFeedList>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignFeedList>
                   <ns1:accountId>100000001</ns1:accountId>
                   <ns1:campaignId>100000003</ns1:campaignId>
                   <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   <ns1:campaignFeed>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:feedItemId>115</ns1:feedItemId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   </ns1:campaignFeed>
                </ns1:campaignFeedList>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Add, update or release(remove) FeedItem information of ad group. <br>
Update will overwrite the old information, so have to include the additional information on every updates. <br>
* To release FeedItem information, update with blank data.<br>
* It is possible to set FeedItem information to ad groups in different campaigns by single request.<br>
* FeedItem information that can be set for a single ad group is up to 20 for each QUICKLINKS, CALLEXTENSION.<br>
* As for CALLEXTENSION, We recommend setting only one phone number per ad group.<br>
* It is not possible to set multiple FeedItem information to an campaignId by single request.<br>


### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignFeedOperation](../data/CampaignFeedOperation.md) | Operation elements for FeedItem information of campaign. <br>FeedItem setting will be overwritten. To release FeedItem information, update the blank data. | 

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
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
<!-- Connect QUICKLINK to campaignId = 100000003 -->
                <ns1:operand>
                   <ns1:accountId>100000001</ns1:accountId>
                   <ns1:campaignId>100000003</ns1:campaignId>
                   <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   <ns1:campaignFeed>
                       <ns1:feedItemId>113</ns1:feedItemId>
                   </ns1:campaignFeed>
                   <ns1:campaignFeed>
                       <ns1:feedItemId>115</ns1:feedItemId>
                   </ns1:campaignFeed>
                 </ns1:operand>
<!-- Connect CALLEXTENSION to campaignId = 100000003 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                 </ns1:operand>
<!-- Disconnect all QUICKLINK from campaignId = 100000007 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000007</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
<!-- Disconnect all CALLEXTENSION from campaignId = 100000007 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000007</ns1:campaignId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
<!-- In case of specifying DESKTOP for devicePlatform of campaignId = 100000008 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000008</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- In case of specifying SMART_PHONE for devicePlatform of campaignId = 100000009 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000009</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- In case of specifying NONE for devicePlatform of campaignId = 100000010 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000010</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
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
| rval | [CampaignFeedReturnValue](../data/CampaignFeedReturnValue.md) | This object is a container for FeeItem information set on campaign which includes operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000003</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>113</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                        <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000003</ns1:campaignId>
                            <ns1:feedItemId>114</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                        <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                    </ns1:campaignFeedList>
               </ns1:values>
               <ns1:values>
                   <ns1:operationSucceeded>true</ns1:operationSucceeded>
                   <ns1:campaignFeedList>
                       <ns1:accountId>100000001</ns1:accountId>
                       <ns1:campaignId>100000003</ns1:campaignId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       <ns1:campaignFeed>
                           <ns1:accountId>100000001</ns1:accountId>
                           <ns1:campaignId>100000003</ns1:campaignId>
                           <ns1:feedItemId>115</ns1:feedItemId>
                           <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       </ns1:campaignFeed>
                       <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                   </ns1:campaignFeedList>
                </ns1:values>
<!-- Response of deleting CALLEXTENSION by SET -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000007</ns1:campaignId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                    </ns1:campaignFeedList>
                </ns1:values>
<!-- Response of deleting QUICKLINK by SET -->
                 <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000007</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                    </ns1:campaignFeedList>
                </ns1:values>
 <!-- In case of specifying DESKTOP for devicePlatform of campaignId = 100000008 -->
                 <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000008</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                        <ns1:campaignFeed>
                            <ns1:accountId>100000001</ns1:accountId>
                            <ns1:campaignId>100000008</ns1:campaignId>
                            <ns1:feedItemId>113</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                    </ns1:campaignFeedList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
