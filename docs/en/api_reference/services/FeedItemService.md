# FeedItemService
FeedItemService is to get, add, update, or remove Feed Item information.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/FeedItemService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/FeedItemService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Get, add, update, or remove Feed Item information

#### Operation
Describes operation provided by FeedItemService.

## get
Get Feed Item information.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Required | [FeedItemSelector](../data/FeedItemSelector.md) | Specify Feed Item information for operations. |

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
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
        <ns1:placeholderTypes>CALLOUT</ns1:placeholderTypes>
        <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
        <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
        <ns1:advanced>TRUE</ns1:advanced>
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
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedItemPage](../data/FeedItemPage.md) | Stores information of Feed Item |

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>FeedItemService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.285</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>7</ns1:totalNumEntries>
            <ns1:Page.Type>FeedItemPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:feedItemId>113</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
                     <ns1:reviewFeedAttributeValue><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:reviewFeedAttributeValue>
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
                  <ns1:reviewCustomParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:feedItemId>114</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                     <ns1:placeholderField>ADDITIONAL_ADVANCED_URLS</ns1:placeholderField>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/url1</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/url2</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                     <ns1:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns1:placeholderField>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp/url1</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp/url2</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
                     <ns1:reviewFeedAttributeValue><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:reviewFeedAttributeValue>
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
                  <ns1:reviewCustomParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:feedItemId>115</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
                     <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>21521</ns1:accountId>
                  <ns1:feedFolderId>999999</ns1:feedFolderId>
                  <ns1:feedItemId>100000</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                     <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                     <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
                     <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
                     <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
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
                     <ns1:targetingCampaignId>999999</ns1:targetingCampaignId>
                  </ns1:targetingCampaign>
                  <ns1:targetingAdGroup>
                     <ns1:targetingAdGroupId>999999</ns1:targetingAdGroupId>
                  </ns1:targetingAdGroup>
                  <ns1:targetingKeyword>
                     <ns1:text>keyword keyword keyword keyword</ns1:text>
                     <ns1:matchType>PHRASE</ns1:matchType>
                  </ns1:targetingKeyword>
                  <ns1:geoTargeting>
                    <ns1:targetId>JP-0001-0010</ns1:targetId>
                    <ns1:type>LOCATION</ns1:type>
                    <ns1:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns1:geoTargetingRestriction>
                  </ns1:geoTargeting>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>21521</ns1:accountId>
                  <ns1:feedItemId>100000</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                     <ns1:feedAttributeId>999999</ns1:feedAttributeId>
                     <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:feedItemId>200000001</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>CALLOUT_TEXT</ns1:placeholderField>
                     <ns1:feedAttributeValue>modify Text</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:placeholderType>CALLOUT</ns1:placeholderType>
                  <ns1:startDate>20151231</ns1:startDate>
                  <ns1:endDate>20200101</ns1:endDate>
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
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Add Feed Item information.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Required | [FeedItemOperation](../data/FeedItemOperation.md) | FeedItem information for operation and list of operations |

##### Request Sample (QuickLinks)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute  xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute  xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
          <ns1:scheduling>
            <ns1:schedules>
              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
              <ns1:startHour>14</ns1:startHour>
              <ns1:startMinute>ZERO</ns1:startMinute>
              <ns1:endHour>15</ns1:endHour>
              <ns1:endMinute>FIFTEEN</ns1:endMinute>
            </ns1:schedules>
          </ns1:scheduling>
          <ns1:customParameters>
            <ns1:isRemove>FALSE</ns1:isRemove>
            <ns1:parameters>
              <ns1:key>site</ns1:key>
              <ns1:value>yahoo</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id1</ns1:key>
              <ns1:value>1234</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id2</ns1:key>
              <ns1:value>a7h59A98yu</ns1:value>
            </ns1:parameters>
          </ns1:customParameters>
          <ns1:advanced>TRUE</ns1:advanced>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample (Call Extensions)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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

##### Request Sample （Ad Customizer）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
            <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
            <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute  xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
            <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
            <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz
            </ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
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
            <ns1:targetingCampaignId>999999</ns1:targetingCampaignId>
          </ns1:targetingCampaign>
          <ns1:targetingAdGroup>
            <ns1:targetingAdGroupId>999999</ns1:targetingAdGroupId>
          </ns1:targetingAdGroup>
          <ns1:targetingKeyword>
            <ns1:text>keyword keyword keyword keyword</ns1:text>
            <ns1:matchType>PHRASE</ns1:matchType>
          </ns1:targetingKeyword>
          <ns1:geoTargeting>
            <ns1:targetId>JP-0001-0010</ns1:targetId>
            <ns1:type>LOCATION</ns1:type>
            <ns1:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns1:geoTargetingRestriction>
          </ns1:geoTargeting>
        </ns1:operand>
        <ns1:operand>
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:feedItemAttribute  xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
            <ns1:feedAttributeId>999999</ns1:feedAttributeId>
            <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Callout option)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:placeholderType>CALLOUT</ns1:placeholderType>
        <ns1:operand>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALLOUT_TEXT</ns1:placeholderField>
            <ns1:feedAttributeValue>sample Text</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
         <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
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
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (adding multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
               <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                  <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                  <ns1:placeholderField>ADDITIONAL_ADVANCED_URLS</ns1:placeholderField>
                  <ns1:feedAttributeValues>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp/url1</ns1:feedAttributeValue>
                  </ns1:feedAttributeValues>
                  <ns1:feedAttributeValues>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp/url2</ns1:feedAttributeValue>
                  </ns1:feedAttributeValues>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                  <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                  <ns1:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns1:placeholderField>
                  <ns1:feedAttributeValues>
                     <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp/url1</ns1:feedAttributeValue>
                  </ns1:feedAttributeValues>
                  <ns1:feedAttributeValues>
                     <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp/url2</ns1:feedAttributeValue>
                  </ns1:feedAttributeValues>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                  <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&uid={id1}&xid={id2}]]></ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:startDate>20151231</ns1:startDate>
               <ns1:endDate>20200101</ns1:endDate>
               <ns1:scheduling>
                  <ns1:schedules>
                     <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                     <ns1:startHour>14</ns1:startHour>
                     <ns1:startMinute>ZERO</ns1:startMinute>
                     <ns1:endHour>15</ns1:endHour>
                     <ns1:endMinute>FIFTEEN</ns1:endMinute>
                  </ns1:schedules>
               </ns1:scheduling>
               <ns1:customParameters>
                  <ns1:isRemove>FALSE</ns1:isRemove>
                  <ns1:parameters>
                     <ns1:key>site</ns1:key>
                     <ns1:value>yahoo</ns1:value>
                  </ns1:parameters>
                  <ns1:parameters>
                     <ns1:key>id1</ns1:key>
                     <ns1:value>1234</ns1:value>
                  </ns1:parameters>
                  <ns1:parameters>
                     <ns1:key>id2</ns1:key>
                     <ns1:value>a7h59A98yu</ns1:value>
                  </ns1:parameters>
               </ns1:customParameters>
               <ns1:advanced>TRUE</ns1:advanced>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | Container for FeedItem information including operation results |

##### Response Sample (QuickLinks)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000001</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}
              </ns1:reviewFeedAttributeValue>
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
            <ns1:reviewCustomParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:reviewCustomParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (Call Extensions)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >
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
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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

##### Response Sample (Ad Customizer)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
              <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
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
              <ns1:targetingCampaignId>999999</ns1:targetingCampaignId>
            </ns1:targetingCampaign>
            <ns1:targetingAdGroup>
              <ns1:targetingAdGroupId>999999</ns1:targetingAdGroupId>
            </ns1:targetingAdGroup>
            <ns1:targetingKeyword>
              <ns1:text>keyword keyword keyword keyword</ns1:text>
              <ns1:matchType>PHRASE</ns1:matchType>
            </ns1:targetingKeyword>
            <ns1:geoTargeting>
              <ns1:targetId>JP-0001-0010</ns1:targetId>
              <ns1:type>LOCATION</ns1:type>
              <ns1:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns1:geoTargetingRestriction>
            </ns1:geoTargeting>
          </ns1:feedItem>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>21521</ns1:accountId>
            <ns1:feedItemId>100000</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
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

##### Response Sample (Callout option)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
          <ns1:feedItemId>200000001</ns1:feedItemId>
          <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALLOUT_TEXT</ns1:placeholderField>
            <ns1:feedAttributeValue>modify Text</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:placeholderType>CALLOUT</ns1:placeholderType>
         <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
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

##### Response Sample (adding multiple Landing Page URLs)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:feedItemId>200000001</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                     <ns1:placeholderField>ADDITIONAL_ADVANCED_URLS</ns1:placeholderField>
                     <ns1:feedAttributeValues>
                        <ns1:reviewFeedAttributeValue>http://www.yahoo.co.jp/url1</ns1:reviewFeedAttributeValue>
                     </ns1:feedAttributeValues>
                     <ns1:feedAttributeValues>
                        <ns1:reviewFeedAttributeValue>http://www.yahoo.co.jp/url2</ns1:reviewFeedAttributeValue>
                     </ns1:feedAttributeValues>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                     <ns1:reviewFeedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:reviewFeedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                     <ns1:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns1:placeholderField>
                     <ns1:feedAttributeValues>
                        <ns1:reviewFeedAttributeValue>http://portal.mobile.yahoo.co.jp/url1</ns1:reviewFeedAttributeValue>
                     </ns1:feedAttributeValues>
                     <ns1:feedAttributeValues>
                        <ns1:reviewFeedAttributeValue>http://portal.mobile.yahoo.co.jp/url2</ns1:reviewFeedAttributeValue>
                     </ns1:feedAttributeValues>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
                     <ns1:reviewFeedAttributeValue><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:reviewFeedAttributeValue>
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
                  <ns1:reviewCustomParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:feedItem>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Required | [FeedItemOperation](../data/FeedItemOperation.md) | FeeItem information for operation and process details |

##### Request Sample (QuickLinks)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
        <ns1:operand>
          <ns1:feedItemId>200000001</ns1:feedItemId>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
          <ns1:scheduling>
            <ns1:schedules>
              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
              <ns1:startHour>14</ns1:startHour>
              <ns1:startMinute>ZERO</ns1:startMinute>
              <ns1:endHour>15</ns1:endHour>
              <ns1:endMinute>FIFTEEN</ns1:endMinute>
            </ns1:schedules>
          </ns1:scheduling>
          <ns1:customParameters>
            <ns1:isRemove>FALSE</ns1:isRemove>
            <ns1:parameters>
              <ns1:key>site</ns1:key>
              <ns1:value>mysite</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id1</ns1:key>
              <ns1:value>5678</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id2</ns1:key>
              <ns1:value>jFj903Hng8e</ns1:value>
            </ns1:parameters>
          </ns1:customParameters>
          <ns1:advanced>TRUE</ns1:advanced>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Call Extensions)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6"  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
        <ns1:operand>
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:feedItemId>118</ns1:feedItemId>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
            <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
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
          <ns1:feedItemId>118</ns1:feedItemId>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
            <ns1:feedAttributeValue>0120-123-456</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
         <!--startDate,endDate,schedulingの設定を解除する場合 -->
          <ns1:startDate></ns1:startDate>
          <ns1:endDate></ns1:endDate>
          <ns1:scheduling></ns1:scheduling>
        </ns1:operand>
        <ns1:operand>
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:feedItemId>119</ns1:feedItemId>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALL_PHONE_NUMBER</ns1:placeholderField>
            <ns1:feedAttributeValue>0120-111-222</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample （Ad Customizer）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6"  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:feedAttributeValue>2015-02-16T11:22:12+09:00</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
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
            <ns1:targetingCampaignId>999999</ns1:targetingCampaignId>
          </ns1:targetingCampaign>
          <ns1:targetingAdGroup>
            <ns1:targetingAdGroupId>999999</ns1:targetingAdGroupId>
          </ns1:targetingAdGroup>
          <ns1:targetingKeyword>
            <ns1:targetingKeywordId>999999</ns1:targetingKeywordId>
          </ns1:targetingKeyword>
          <ns1:geoTargeting>
            <ns1:targetId>JP-13-0004</ns1:targetId>
            <ns1:geoTargetingRestriction>NONE</ns1:geoTargetingRestriction>
          </ns1:geoTargeting>
        </ns1:operand>
        <ns1:operand>
          <ns1:accountId>1000000001</ns1:accountId>
          <ns1:feedItemId>999999</ns1:feedItemId>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Callout option)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6"  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:placeholderType>CALLOUT</ns1:placeholderType>
        <ns1:operand>
          <ns1:feedItemId>200000001</ns1:feedItemId>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALLOUT_TEXT</ns1:placeholderField>
            <ns1:feedAttributeValue>modify text</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
         <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
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
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (updating FeeItems set with multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
<!-- MulitpleFeedItemAttributeの設定解除 -->           
            <ns1:operand>
               <ns1:feedItemId>200000001</ns1:feedItemId>
               <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                   <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                   <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <!--ADDITIONAL_ADVANCED_URLSの設定解除-->
               <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                  <ns1:placeholderField>ADDITIONAL_ADVANCED_URLS</ns1:placeholderField>
                  <ns1:isRemove>TRUE</ns1:isRemove>
              </ns1:feedItemAttribute>
              <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                   <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                   <ns1:feedAttributeValue>http://www.yahoo.co.jp/mobile</ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
              <!--ADDITIONAL_ADVANCED_MOBILE_URLSの設定解除-->
               <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                  <ns1:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns1:placeholderField>
                  <ns1:isRemove>TRUE</ns1:isRemove>
               </ns1:feedItemAttribute>
               <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                  <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
                  <ns1:feedAttributeValue><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&uid={id1}&xid={id2}]]></ns1:feedAttributeValue>
               </ns1:feedItemAttribute>
               <ns1:startDate>20151231</ns1:startDate>
               <ns1:endDate>20200101</ns1:endDate>
               <ns1:scheduling>
                  <ns1:schedules>
                     <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                     <ns1:startHour>14</ns1:startHour>
                     <ns1:startMinute>ZERO</ns1:startMinute>
                     <ns1:endHour>15</ns1:endHour>
                     <ns1:endMinute>FIFTEEN</ns1:endMinute>
                  </ns1:schedules>
               </ns1:scheduling>
               <ns1:customParameters>
                  <ns1:isRemove>FALSE</ns1:isRemove>
                  <ns1:parameters>
                     <ns1:key>site</ns1:key>
                     <ns1:value>mysite</ns1:value>
                  </ns1:parameters>
                  <ns1:parameters>
                     <ns1:key>id1</ns1:key>
                     <ns1:value>5678</ns1:value>
                  </ns1:parameters>
                  <ns1:parameters>
                     <ns1:key>id2</ns1:key>
                     <ns1:value>jFj903Hng8e</ns1:value>
                  </ns1:parameters>
               </ns1:customParameters>
               <ns1:advanced>TRUE</ns1:advanced>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data type | Description |
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | Container for Feed Item information including operation results |

##### Response Sample (QuickLinks)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000001</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}
              </ns1:reviewFeedAttributeValue>
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
            <ns1:reviewCustomParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:reviewCustomParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (Call Extensions)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >
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
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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

##### Response Sample (Ad Customizer)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>21521</ns1:accountId>
            <ns1:feedFolderId>999999</ns1:feedFolderId>
            <ns1:feedItemId>100000</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
              <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
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
              <ns1:targetingCampaignId>999999</ns1:targetingCampaignId>
            </ns1:targetingCampaign>
            <ns1:targetingAdGroup>
              <ns1:targetingAdGroupId>999999</ns1:targetingAdGroupId>
            </ns1:targetingAdGroup>
            <ns1:targetingKeyword>
              <ns1:text>keyword keyword keyword keyword</ns1:text>
              <ns1:matchType>PHRASE</ns1:matchType>
            </ns1:targetingKeyword>
            <ns1:geoTargeting>
              <ns1:targetId>JP-13-0004</ns1:targetId>
              <ns1:type>LOCATION</ns1:type>
              <ns1:geoTargetingRestriction>NONE</ns1:geoTargetingRestriction>
            </ns1:geoTargeting>
          </ns1:feedItem>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>21521</ns1:accountId>
            <ns1:feedItemId>100000</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
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

##### Response Sample (Callout option)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
          <ns1:feedItemId>200000001</ns1:feedItemId>
          <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALLOUT_TEXT</ns1:placeholderField>
            <ns1:feedAttributeValue>modify Text</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:placeholderType>CALLOUT</ns1:placeholderType>
         <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
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

##### Response Sample (Updating FeeItem set with multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:feedItemId>200000001</ns1:feedItemId>
                  <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp/mobile</ns1:feedAttributeValue>
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
                  <ns1:reviewCustomParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:feedItem>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove the Feed Item details.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Required | [FeedItemOperation](../data/FeedItemOperation.md) | FeedItem information for operation and process details |

##### Request Sample (QuickLinks, including removing multiple Landing Page URLs)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
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
          <ns1:feedItemId>113</ns1:feedItemId>
        </ns1:operand>
        <ns1:operand>
          <ns1:feedItemId>114</ns1:feedItemId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Call Extensions)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
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
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Ad Customizer)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
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
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Callout option)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
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
        <ns1:placeholderType>CALLOUT</ns1:placeholderType>
        <ns1:operand>
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:feedItemId>999999</ns1:feedItemId>
       </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data type | Description |
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | Container for FeedItem information including operation results |

##### Response Sample (QuickLinks, including removing multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:feedItemId>113</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
                     <ns1:reviewFeedAttributeValue><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:reviewFeedAttributeValue>
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
                  <ns1:reviewCustomParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:feedItem>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:feedItem>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:feedItemId>114</ns1:feedItemId>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                     <ns1:placeholderField>ADDITIONAL_ADVANCED_URLS</ns1:placeholderField>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/url1</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://www.yahoo.co.jp/url2</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
                     <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:MultipleFeedItemAttribute">
                     <ns1:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns1:placeholderField>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp/url1</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                     <ns1:feedAttributeValues>
                        <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp/url2</ns1:feedAttributeValue>
                     </ns1:feedAttributeValues>
                  </ns1:feedItemAttribute>
                  <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
                     <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
                     <ns1:reviewFeedAttributeValue><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:reviewFeedAttributeValue>
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
                  <ns1:reviewCustomParameters>
                     <ns1:isRemove>FALSE</ns1:isRemove>
                     <ns1:parameters>
                        <ns1:key>site</ns1:key>
                        <ns1:value>yahoo</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id1</ns1:key>
                        <ns1:value>1234</ns1:value>
                     </ns1:parameters>
                     <ns1:parameters>
                        <ns1:key>id2</ns1:key>
                        <ns1:value>a7h59A98yu</ns1:value>
                     </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:feedItem>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (Call Extensions)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >
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
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
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

##### Response Sample (Ad Customizer)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>21521</ns1:accountId>
            <ns1:feedFolderId>999999</ns1:feedFolderId>
            <ns1:feedItemId>100000</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>1234567890</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>9,999,999.99</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_DATE</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>20151231 235959</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_STRING</ns1:placeholderField>
              <ns1:feedAttributeId>999999</ns1:feedAttributeId>
              <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>LINK_TEXT</ns1:placeholderField>
              <ns1:feedAttributeValue>abcdefghijklmnopqrstuvwxyz</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
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
              <ns1:targetingCampaignId>999999</ns1:targetingCampaignId>
            </ns1:targetingCampaign>
            <ns1:targetingAdGroup>
              <ns1:targetingAdGroupId>999999</ns1:targetingAdGroupId>
            </ns1:targetingAdGroup>
            <ns1:targetingKeyword>
              <ns1:text>keyword keyword keyword keyword</ns1:text>
              <ns1:matchType>PHRASE</ns1:matchType>
            </ns1:targetingKeyword>
            <ns1:geoTargeting>
              <ns1:targetId>JP-0001-0010</ns1:targetId>
              <ns1:type>LOCATION</ns1:type>
              <ns1:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns1:geoTargetingRestriction>
            </ns1:geoTargeting>
          </ns1:feedItem>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>21521</ns1:accountId>
            <ns1:feedItemId>100000</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
              <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
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

##### Response Sample (Callout option)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
          <ns1:feedItemId>200000001</ns1:feedItemId>
          <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
          <ns1:feedItemAttribute xsi:type="ns1:SimpleFeedItemAttribute">
            <ns1:placeholderField>CALLOUT_TEXT</ns1:placeholderField>
            <ns1:feedAttributeValue>modify Text</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:placeholderType>CALLOUT</ns1:placeholderType>
         <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
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

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
