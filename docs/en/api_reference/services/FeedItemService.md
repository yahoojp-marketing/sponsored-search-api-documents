# FeedItemService
FeedItemService is to get, add, upgrade, or delete the FeedItem information.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/FeedItemService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/FeedItemService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Get, add, upgrade, or delete the FeedItem information
#### Operation
Describes operation provided by FeedItemService.
## get
### Request
Get FeedItem information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | Req | [FeedItemSelector](../data/FeedItemSelector.md) | FeedItem information relate to the operations to apply. | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>	
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:feedItemIds>12</ns1:feedItemIds>
                <ns1:feedItemIds>13</ns1:feedItemIds>
                <ns1:placeholderTypes>QUICKLINK</ns1:placeholderTypes>
                <ns1:placeholderTypes>CALLEXTENSION</ns1:placeholderTypes>
                <ns1:placeholderTypes>AD_CUSTOMIZER</ns1:placeholderTypes>
                <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
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
                <ns1:feedItemIds>12</ns1:feedItemIds>
                <ns1:feedItemIds>13</ns1:feedItemIds>
                <ns1:placeholderTypes>QUICKLINK</ns1:placeholderTypes>
                <ns1:placeholderTypes>CALLEXTENSION</ns1:placeholderTypes>
                <ns1:placeholderTypes>AD_CUSTOMIZER</ns1:placeholderTypes>
                <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
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
| rval | [FeedItemPage](../data/FeedItemPage.md) | FeedItem information relate to the operations to apply. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
               <ns1:totalNumEntries>4</ns1:totalNumEntries>
                <ns1:Page.Type>FeedItemPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>113</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT　</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!TOP　</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL　</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp　</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:startDate>20120112</ns1:startDate>
                        <ns1:endDate>20120113</ns1:endDate>
                        <ns1:scheduling>
                           <ns1:schedules>
                              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                              <ns1:startHour>12</ns1:startHour>
                              <ns1:startMinute>ZERO</ns1:startMinute>
                              <ns1:endHour>13</ns1:endHour>
                              <ns1:endMinute>FIFTEEN</ns1:endMinute>
                           </ns1:schedules>
                           <ns1:schedules>
                              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                              <ns1:startHour>12</ns1:startHour>
                              <ns1:startMinute>ZERO</ns1:startMinute>
                              <ns1:endHour>13</ns1:endHour>
                              <ns1:endMinute>FIFTEEN</ns1:endMinute>
                           </ns1:schedules>
                           <ns1:schedules>
                              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                              <ns1:startHour>12</ns1:startHour>
                              <ns1:startMinute>ZERO</ns1:startMinute>
                              <ns1:endHour>13</ns1:endHour>
                              <ns1:endMinute>FIFTEEN</ns1:endMinute>
                           </ns1:schedules>
                        </ns1:scheduling> 
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>114</ns1:feedItemId>
                        <ns1:approvalStatus>PRE_DISAPPROVED　</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes>Z005　</ns1:disapprovalReasonCodes>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER　</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-111-222　</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION　</ns1:placeholderType>
                        <ns1:devicePreference>SMART_PHONE　</ns1:devicePreference>
                        <ns1:startDate>20120112</ns1:startDate>
                        <ns1:endDate>20120113</ns1:endDate>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>115</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW </ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER </ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-123-456 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>0120-456-789 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION </ns1:placeholderType>
                        <ns1:devicePreference>SMART_PHONE </ns1:devicePreference>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>10000</ns1:accountId>
                        <ns1:feedFolderId>999999</ns1:feedFolderId>
                        <ns1:feedItemId>100000</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_DATE </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_STRING </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>AD_CUSTOMIZER </ns1:placeholderType>
                        <ns1:targetingCampaign>
                            <ns1:targetingCampaignId>999999 </ns1:targetingCampaignId>
                        </ns1:targetingCampaign>
                        <ns1:targetingAdGroup>
                            <ns1:targetingAdGroupId>999999 </ns1:targetingAdGroupId>
                        </ns1:targetingAdGroup>
                        <ns1:targetingKeyword>
                            <ns1:feedKeywordId>999999</ns1:feedKeywordId>
                            <ns1:text>keyword keyword keyword keyword keyword</ns1:text>
                            <ns1:matchType>EXACT</ns1:matchType>
                        </ns1:targetingKeyword>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request
Add the information related to FeedItem.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | Req | [FeedItemOperation](../data/FeedItemOperation.md) | Operation elements for FeedItem information. | 

##### Request Sample [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!Top</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!News</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/news</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For QUICKLINK] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!Top</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!News</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/news</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For CALLEXTENSION] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedFolderId>999999</ns1:feedFolderId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_STRING </ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz
                        </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER </ns1:placeholderType>
                    <ns1:startDate>20150217</ns1:startDate>
                    <ns1:endDate>20150217</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                    <ns1:targetingCampaign>
                        <ns1:targetingCampaignId>999999 </ns1:targetingCampaignId>
                    </ns1:targetingCampaign>
                    <ns1:targetingAdGroup>
                        <ns1:targetingAdGroupId>999999 </ns1:targetingAdGroupId>
                    </ns1:targetingAdGroup>
                    <ns1:targetingKeyword>
                        <ns1:text>keyword keyword keyword keyword</ns1:text>
                        <ns1:matchType>PHRASE</ns1:matchType>
                    </ns1:targetingKeyword>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>1234567890 </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER </ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedFolderId>999999</ns1:feedFolderId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>1234567890 </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>9,999,999.99 </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_DATE </ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_STRING </ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER </ns1:placeholderType>
                    <ns1:startDate>20150217</ns1:startDate>
                    <ns1:endDate>20150217</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                    <ns1:targetingCampaign>
                        <ns1:targetingCampaignId>999999 </ns1:targetingCampaignId>
                    </ns1:targetingCampaign>
                    <ns1:targetingAdGroup>
                        <ns1:targetingAdGroupId>999999 </ns1:targetingAdGroupId>
                    </ns1:targetingAdGroup>
                    <ns1:targetingKeyword>
                        <ns1:text>keyword keyword keyword keyword</ns1:text>
                        <ns1:matchType>PHRASE</ns1:matchType>
                    </ns1:targetingKeyword>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                        <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                        <ns1:feedAttributeValue>1234567890 </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER </ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | Container for FeedItem information including operation results. | 

##### Response Sample [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>113</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!TOP</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>114</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!News</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp/News</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>115</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>116</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>-1</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.285</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>21521</ns1:accountId>
                        <ns1:feedFolderId>999999</ns1:feedFolderId>
                        <ns1:feedItemId>100000</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_DATE </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_STRING </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT </ns1:placeholderField>
                            <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>AD_CUSTOMIZER </ns1:placeholderType>
                        <ns1:startDate>20150217</ns1:startDate>
                        <ns1:endDate>20150217</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                        <ns1:targetingCampaign>
                            <ns1:targetingCampaignId>999999 </ns1:targetingCampaignId>
                        </ns1:targetingCampaign>
                        <ns1:targetingAdGroup>
                            <ns1:targetingAdGroupId>999999 </ns1:targetingAdGroupId>
                        </ns1:targetingAdGroup>
                        <ns1:targetingKeyword>
                            <ns1:text>keyword keyword keyword keyword </ns1:text>
                            <ns1:matchType>PHRASE</ns1:matchType>
                        </ns1:targetingKeyword>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>21521</ns1:accountId>
                        <ns1:feedItemId>100000</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>	
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request
| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [FeedItemOperation](../data/FeedItemOperation.md) | Operation elements for FeedItem information. | 

##### Request Sample [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>113</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!Top</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>113</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!Top</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePreference></ns1:devicePreference>
<!-- Cancel setting of startDate, endDate, scheduling -->
                    <ns1:startDate></ns1:startDate>
                    <ns1:endDate></ns1:endDate>
                    <ns1:scheduling></ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>114</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!News</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/news</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For QUICKLINK] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>113</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!Top</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>113</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!Top</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePreference></ns1:devicePreference>
<!-- Cancel setting of startDate, endDate, scheduling -->
                    <ns1:startDate></ns1:startDate>
                    <ns1:endDate></ns1:endDate>
                    <ns1:scheduling></ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>114</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                        <ns1:feedAttributeValue>Y!News</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/news</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [For CALLEXTENSION]
```xml
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>118</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:deliveryScheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>118</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
<!-- Cancel setting of startDate, endDate, scheduling -->
                    <ns1:startDate></ns1:startDate>
                    <ns1:endDate></ns1:endDate>
                    <ns1:scheduling></ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>119</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For CALLEXTENSION] 
```xml
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>118</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:startDate>20130910</ns1:startDate>
                    <ns1:endDate>20130920</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:deliveryScheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>118</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
<!-- Cancel setting of startDate, endDate, scheduling -->
                    <ns1:startDate></ns1:startDate>
                    <ns1:endDate></ns1:endDate>
                    <ns1:scheduling></ns1:scheduling>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>119</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                        <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
               <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedItemId>999999</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>1234567890</ns1:feedAttribute Value>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttribute Value>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>2015-02-16T11:22:12+09:00 </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                    <ns1:startDate>20150217</ns1:startDate>
                    <ns1:endDate>20150217</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                    <ns1:targetingCampaign>
                        <ns1:targetingCampaignId>999999</ns1:targeting CampaignId>
                    </ns1:targetingCampaign>
                    <ns1:targetingAdGroup>
                        <ns1:targetingAdGroupId>999999</ns1:targeting AdGroupId>
                    </ns1:targetingAdGroup>
                    <ns1:targetingKeyword>
                        <ns1:feedKeywordId>999999</ns1:feedKeywordId>
                    </ns1:targetingKeyword>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedItemId>999999</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>1234567890</ns1:feedAttribute Value>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
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
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
               <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedItemId>999999</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>1234567890</ns1:feedAttribute Value>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttribute Value>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>2015-02-16T11:22:12+09:00 </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz </ns1:feedAttributeValue>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                    <ns1:startDate>20150217</ns1:startDate>
                    <ns1:endDate>20150217</ns1:endDate>
                    <ns1:scheduling>
                        <ns1:schedules>
                            <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                            <ns1:startHour>14</ns1:startHour>
                            <ns1:startMinute>ZERO</ns1:startMinute>
                            <ns1:endHour>15</ns1:endHour>
                            <ns1:endMinute>FIFTEEN</ns1:endMinute>
                        </ns1:schedules>
                    </ns1:scheduling>
                    <ns1:targetingCampaign>
                        <ns1:targetingCampaignId>999999</ns1:targeting CampaignId>
                    </ns1:targetingCampaign>
                    <ns1:targetingAdGroup>
                        <ns1:targetingAdGroupId>999999</ns1:targeting AdGroupId>
                    </ns1:targetingAdGroup>
                    <ns1:targetingKeyword>
                        <ns1:feedKeywordId>999999</ns1:feedKeywordId>
                    </ns1:targetingKeyword>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedItemId>999999</ns1:feedItemId>
                    <ns1:feedItemAttribute>
                        <ns1:feedAttributeValue>1234567890</ns1:feedAttribute Value>
                    </ns1:feedItemAttribute>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder rType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data type | Description | 
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | Container for FeedItem information including operation results. | 

##### Response Sample [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>113</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!TOP</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>Yahoo!News</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>http://www.yahoo.co.jp/News</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>113</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!TOP</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>Yahoo!News</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>http://www.yahoo.co.jp/News</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>114</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!News</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>Yahoo!TOP</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp/News</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>http://www.yahoo.co.jp/</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>115</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>0120-111-222</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>115</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>0120-111-222</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>116</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>0120-123-456</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>-1</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>1.0858</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue
                </ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>21521</ns1:accountId>
                        <ns1:feedFolderId>100000</ns1:feedFolderId>
                        <ns1:feedItemId>999999</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                            <ns1:feedAttributeId>100000</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>TEST</ns1:feedAttribute Value>
                            <ns1:reviewFeedAttributeValue>1234567890 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                            <ns1:feedAttributeId>100000</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>TEST</ns1:feedAttribute Value>
                            <ns1:reviewFeedAttributeValue>9,999,999.99 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_DATE </ns1:placeholderField>
                            <ns1:feedAttributeId>100000</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>TEST</ns1:feedAttribute Value>
                            <ns1:reviewFeedAttributeValue>2015-02-16T11:22:12 +09:00</ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_STRING </ns1:placeholderField>
                            <ns1:feedAttributeId>100000</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>TEST</ns1:feedAttribute Value>
                            <ns1:reviewFeedAttributeValue>abcdefghijklmnop qrstuvwxyz </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                        <ns1:startDate>20150217</ns1:startDate>
                        <ns1:endDate>20150217</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                        <ns1:targetingCampaign>
                            <ns1:targetingCampaignId>999999</ns1:targeting CampaignId>
                        </ns1:targetingCampaign>
                        <ns1:targetingAdGroup>
                            <ns1:targetingAdGroupId>999999</ns1:targeting AdGroupId>
                        </ns1:targetingAdGroup>
                        <ns1:targetingKeyword>
                            <ns1:feedKeywordId>999999</ns1:feedKeywordId>
                            <ns1:text>aaa aaa aaa</ns1:text>
                            <ns1:matchType>PHRASE</ns1:matchType>
                        </ns1:targetingKeyword>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>21521</ns1:accountId>
                        <ns1:feedFolderId>100000</ns1:feedFolderId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                            <ns1:feedAttributeId>100000</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>TEST</ns1:feedAttribute Value>
                            <ns1:reviewFeedAttributeValue>1234567890 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [FeedItemOperation](../data/FeedItemOperation.md) | Operation elements for FeedItem information. | 

##### Request Sample [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>113</ns1:feedItemId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>114</ns1:feedItemId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For QUICKLINK] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>113</ns1:feedItemId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>114</ns1:feedItemId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>115</ns1:feedItemId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>116</ns1:feedItemId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For CALLEXTENSION] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>115</ns1:feedItemId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>116</ns1:feedItemId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>999999</ns1:feedItemId>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:feedItemId>999999</ns1:feedItemId>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data type | Description | 
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | Operation elements for FeedItem information. | 

##### Response Sample [For QUICKLINK]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>113</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!TOP</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>Yahoo!News</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>http://www.yahoo.co.jp/News</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>114</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                            <ns1:feedAttributeValue>Yahoo!News</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>Yahoo!TOP</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>LINK_URL</ns1:placeholderField>
                            <ns1:feedAttributeValue>http://www.yahoo.co.jp/News</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>http://www.yahoo.co.jp/</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample [For CALLEXTENSION]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>115</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>0120-111-222</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:startDate>20130910</ns1:startDate>
                        <ns1:endDate>20130920</ns1:endDate>
                        <ns1:scheduling>
                            <ns1:schedules>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>14</ns1:startHour>
                                <ns1:startMinute>ZERO</ns1:startMinute>
                                <ns1:endHour>15</ns1:endHour>
                                <ns1:endMinute>FIFTEEN</ns1:endMinute>
                            </ns1:schedules>
                        </ns1:scheduling>
                    </ns1:feedItem>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedItemId>116</ns1:feedItemId>
                        <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                            <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
                            <ns1:editFeedAttributeValue>0120-123-456</ns1:editFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample [For AD_CUSTOMIZER] 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedItemService</ns1:service>
            <ns1:remainingQuota>-1</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.3192</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1: ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedItem>
                        <ns1:accountId>10000</ns1:accountId>
                        <ns1:feedFolderId>999999</ns1:feedFolderId>
                        <ns1:feedItemId>100000</ns1:feedItemId>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_DATE </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:feedItemAttribute>
                            <ns1:placeholderField>AD_CUSTOMIZER_STRING </ns1:placeholderField>
                            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                            <ns1:feedAttributeValue>1234567890123456789 </ns1:feedAttributeValue>
                            <ns1:reviewFeedAttributeValue>9876543210987654321 </ns1:reviewFeedAttributeValue>
                        </ns1:feedItemAttribute>
                        <ns1:placeholderType>AD_CUSTOMIZER </ns1:placeholderType>
                        <ns1:targetingCampaign>
                            <ns1:targetingCampaignId>999999 </ns1:targetingCampaignId>
                        </ns1:targetingCampaign>
                        <ns1:targetingAdGroup>
                            <ns1:targetingAdGroupId>999999 </ns1:targetingAdGroupId>
                        </ns1:targetingAdGroup>
                        <ns1:targetingKeyword>
                            <ns1:feedKeywordId>999999</ns1:feedKeywordId>
                            <ns1:text>keyword keyword keyword keyword keyword</ns1:text>
                            <ns1:matchType>EXACT</ns1:matchType>
                        </ns1:targetingKeyword>
                    </ns1:feedItem>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
