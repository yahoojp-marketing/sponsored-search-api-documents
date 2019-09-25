# FeedItemService

FeedItemService is to get, add, update, or remove Feed Item information.

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://ss.yahooapis.jp/services/V201909/FeedItemService?wsdl |
| sandbox     | https://sandbox.ss.yahooapis.jp/services/V201909/FeedItemService?wsdl  |

#### Namespace

http://ss.yahooapis.jp/V201909/FeedItem

#### Service Overview

Get, add, update, or remove Feed Item information

#### Operation

Explains operations provided by FeedItemService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)
+ [setTrademarkStatus](#settrademarkstatus)

## get

### Request

Get Feed Item information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [FeedItemSelector](../data/FeedItem/FeedItemSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>100000001</accountId>
        <feedItemIds>200000001</feedItemIds>
        <feedItemIds>200000002</feedItemIds>
        <feedItemIds>200000003</feedItemIds>
        <feedItemIds>200000004</feedItemIds>
        <feedItemIds>200000005</feedItemIds>
        <feedFolderIds>300000001</feedFolderIds>
        <feedFolderIds>300000002</feedFolderIds>
        <feedFolderIds>300000003</feedFolderIds>
        <feedFolderIds>300000004</feedFolderIds>
        <feedFolderIds>300000005</feedFolderIds>
        <placeholderTypes>QUICKLINK</placeholderTypes>
        <placeholderTypes>CALLEXTENSION</placeholderTypes>
        <placeholderTypes>AD_CUSTOMIZER</placeholderTypes>
        <placeholderTypes>CALLOUT</placeholderTypes>
        <placeholderTypes>STRUCTURED_SNIPPET</placeholderTypes>
        <approvalStatuses>APPROVED</approvalStatuses>
        <approvalStatuses>APPROVED_WITH_REVIEW</approvalStatuses>
        <approvalStatuses>REVIEW</approvalStatuses>
        <approvalStatuses>PRE_DISAPPROVED</approvalStatuses>
        <approvalStatuses>POST_DISAPPROVED</approvalStatuses>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>1000</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Get Feed Item information.

| Parameter | Data Type |
| -------- | ------- |
| rval | [FeedItemPage](../data/FeedItem/FeedItemPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423170</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>FeedItemPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>300000001</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:trademarkStatus>NO_RESTRICTION</ns2:trademarkStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>quicklink feedItem.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000002</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>update quicklink feedItem.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000003</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALL_PHONE_NUMBER</ns2:placeholderField>
              <ns2:feedAttributeValue>0120-111-222</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLEXTENSION</ns2:placeholderType>
            <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000004</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALLOUT_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>callout text.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLOUT</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>300000001</ns2:feedFolderId>
            <ns2:feedItemId>200000005</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeValue>test</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeValue>20151231 235959</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeValue>1234567890</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeValue>9,999,999.99</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:targetingCampaign>
              <ns2:targetingCampaignId>400000001</ns2:targetingCampaignId>
            </ns2:targetingCampaign>
            <ns2:targetingAdGroup>
              <ns2:targetingAdGroupId>500000001</ns2:targetingAdGroupId>
            </ns2:targetingAdGroup>
            <ns2:targetingKeyword>
              <ns2:targetingKeywordId>600000001</ns2:targetingKeywordId>
              <ns2:text>test keyword</ns2:text>
              <ns2:matchType>EXACT</ns2:matchType>
            </ns2:targetingKeyword>
            <ns2:geoTargeting>
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:type>LOCATION</ns2:type>
              <ns2:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_HEADER</ns2:placeholderField>
              <ns2:feedAttributeValue>ブランド</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_VALUES</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>NIKE</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>ADIDAS</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>PUMA</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>STRUCTURED_SNIPPET</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request

Add Feed Item information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [FeedItemOperation](../data/FeedItem/FeedItemOperation.md) |

##### Request Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <placeholderType>QUICKLINK</placeholderType>
        <operand>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_TEXT</placeholderField>
            <feedAttributeValue>quicklink feedItem.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_URL</placeholderField>
            <feedAttributeValue>http://www.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_MOBILE_URL</placeholderField>
            <feedAttributeValue>http://portal.mobile.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>TRACKING_URL</placeholderField>
            <feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 1.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 2.</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190830</startDate>
          <endDate>20190930</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>MONDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
          <customParameters>
            <parameters>
              <key>site</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id1</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id2</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Call Extensions)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <placeholderType>CALLEXTENSION</placeholderType>
        <operand>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>CALL_PHONE_NUMBER</placeholderField>
            <feedAttributeValue>0120-111-222</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190830</startDate>
          <endDate>20190930</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>MONDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Ad Customizer)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <placeholderType>AD_CUSTOMIZER</placeholderType>
        <operand>
          <feedFolderId>300000001</feedFolderId>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>1</feedAttributeId>
            <feedAttributeValue>test</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>2</feedAttributeId>
            <feedAttributeValue>20151231 235959</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>3</feedAttributeId>
            <feedAttributeValue>1234567890</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>4</feedAttributeId>
            <feedAttributeValue>9,999,999.99</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190830</startDate>
          <endDate>20190930</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>MONDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
          <targetingCampaign>
            <targetingCampaignId>400000001</targetingCampaignId>
          </targetingCampaign>
          <targetingAdGroup>
            <targetingAdGroupId>500000001</targetingAdGroupId>
          </targetingAdGroup>
          <targetingKeyword>
            <text>test keyword</text>
            <matchType>EXACT</matchType>
          </targetingKeyword>
          <geoTargeting>
            <targetId>JP-01-0010</targetId>
            <type>LOCATION</type>
            <geoTargetingRestriction>LOCATION_OF_PRESENCE</geoTargetingRestriction>
          </geoTargeting>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Callout option)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <placeholderType>CALLOUT</placeholderType>
        <operand>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>CALLOUT_TEXT</placeholderField>
            <feedAttributeValue>callout text.</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190830</startDate>
          <endDate>20190930</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>MONDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Category Text)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <placeholderType>STRUCTURED_SNIPPET</placeholderType>
        <operand>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>STRUCTURED_SNIPPET_HEADER</placeholderField>
            <feedAttributeValue>ブランド</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="MultipleFeedItemAttribute">
            <placeholderField>STRUCTURED_SNIPPET_VALUES</placeholderField>
            <feedAttributeValues>
              <feedAttributeValue>NIKE</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>ADIDAS</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>PUMA</feedAttributeValue>
            </feedAttributeValues>
          </feedItemAttribute>
          <startDate>20190830</startDate>
          <endDate>20190930</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>MONDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(adding multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <placeholderType>QUICKLINK</placeholderType>
        <operand>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_TEXT</placeholderField>
            <feedAttributeValue>quicklink feedItem.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_URL</placeholderField>
            <feedAttributeValue>http://www.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="MultipleFeedItemAttribute">
            <placeholderField>ADDITIONAL_ADVANCED_URLS</placeholderField>
            <feedAttributeValues>
              <feedAttributeValue>http://www.yahoo.co.jp/lp1/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://www.yahoo.co.jp/lp2/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://www.yahoo.co.jp/lp3/</feedAttributeValue>
            </feedAttributeValues>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_MOBILE_URL</placeholderField>
            <feedAttributeValue>http://portal.mobile.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="MultipleFeedItemAttribute">
            <placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</placeholderField>
            <feedAttributeValues>
              <feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp1/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp2/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp3/</feedAttributeValue>
            </feedAttributeValues>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>TRACKING_URL</placeholderField>
            <feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 1.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 2.</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190830</startDate>
          <endDate>20190930</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>MONDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
          <customParameters>
            <parameters>
              <key>site</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id1</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id2</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Add Feed Item information.

| Parameter | Data Type |
| -------- | ------- |
| rval | [FeedItemReturnValue](../data/FeedItem/FeedItemReturnValue.md) |

##### Response Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423191</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>update quicklink feedItem.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Call Extensions)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423214</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000003</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALL_PHONE_NUMBER</ns2:placeholderField>
              <ns2:feedAttributeValue>0120-111-222</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLEXTENSION</ns2:placeholderType>
            <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Ad Customizer)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423230</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>300000001</ns2:feedFolderId>
            <ns2:feedItemId>200000005</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeValue>test</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeValue>20151231 235959</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeValue>1234567890</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeValue>9,999,999.99</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:targetingCampaign>
              <ns2:targetingCampaignId>400000001</ns2:targetingCampaignId>
            </ns2:targetingCampaign>
            <ns2:targetingAdGroup>
              <ns2:targetingAdGroupId>500000001</ns2:targetingAdGroupId>
            </ns2:targetingAdGroup>
            <ns2:targetingKeyword>
              <ns2:targetingKeywordId>600000001</ns2:targetingKeywordId>
              <ns2:text>test keyword</ns2:text>
              <ns2:matchType>EXACT</ns2:matchType>
            </ns2:targetingKeyword>
            <ns2:geoTargeting>
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:type>LOCATION</ns2:type>
              <ns2:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Callout option)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423245</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000004</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALLOUT_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>callout text.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLOUT</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Category Text)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423258</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_HEADER</ns2:placeholderField>
              <ns2:feedAttributeValue>ブランド</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_VALUES</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>NIKE</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>ADIDAS</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>PUMA</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>STRUCTURED_SNIPPET</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(adding multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423273</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000002</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>update quicklink feedItem.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>MONDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

### Request

Set Feed Item information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [FeedItemOperation](../data/FeedItem/FeedItemOperation.md) |

##### Request Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <placeholderType>QUICKLINK</placeholderType>
        <operand>
          <feedItemId>200000001</feedItemId>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_TEXT</placeholderField>
            <feedAttributeValue>update quicklink feedItem.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_URL</placeholderField>
            <feedAttributeValue>http://www2.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_MOBILE_URL</placeholderField>
            <feedAttributeValue>http://mobile.mobile.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>TRACKING_URL</placeholderField>
            <feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site2}&amp;pid={_id3}&amp;vid={_id4}</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 1.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 2.</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190831</startDate>
          <endDate>20191001</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>FRIDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
          <customParameters>
            <parameters>
              <key>site2</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id3</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id4</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Call Extensions)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <placeholderType>CALLEXTENSION</placeholderType>
        <operand>
          <feedItemId>200000003</feedItemId>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>CALL_PHONE_NUMBER</placeholderField>
            <feedAttributeValue>0120-888-999</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190831</startDate>
          <endDate>20191001</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>FRIDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Ad Customizer)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <placeholderType>AD_CUSTOMIZER</placeholderType>
        <operand>
          <feedItemId>200000005</feedItemId>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>1</feedAttributeId>
            <feedAttributeValue>set test</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>2</feedAttributeId>
            <feedAttributeValue>20171231 235959</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>3</feedAttributeId>
            <feedAttributeValue>9012345678</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <feedAttributeId>4</feedAttributeId>
            <feedAttributeValue>8,888,888.88</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190831</startDate>
          <endDate>20191001</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>FRIDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
          <targetingCampaign>
            <targetingCampaignId>0</targetingCampaignId>
          </targetingCampaign>
          <targetingAdGroup>
            <targetingAdGroupId>0</targetingAdGroupId>
          </targetingAdGroup>
          <targetingKeyword>
            <text>set test keyword</text>
            <matchType>EXACT</matchType>
          </targetingKeyword>
          <geoTargeting>
            <targetId>JP-01-0011</targetId>
            <type>LOCATION</type>
            <geoTargetingRestriction>LOCATION_OF_PRESENCE</geoTargetingRestriction>
          </geoTargeting>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Callout option)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <placeholderType>CALLOUT</placeholderType>
        <operand>
          <feedItemId>200000004</feedItemId>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>CALLOUT_TEXT</placeholderField>
            <feedAttributeValue>set callout text.</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190831</startDate>
          <endDate>20191001</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>FRIDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Category Text)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <placeholderType>STRUCTURED_SNIPPET</placeholderType>
        <operand>
          <feedItemId>200000001</feedItemId>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>STRUCTURED_SNIPPET_HEADER</placeholderField>
            <feedAttributeValue>ブランド</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="MultipleFeedItemAttribute">
            <placeholderField>STRUCTURED_SNIPPET_VALUES</placeholderField>
            <feedAttributeValues>
              <feedAttributeValue>FILA</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>ASICS</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>CHAMPION</feedAttributeValue>
            </feedAttributeValues>
          </feedItemAttribute>
          <startDate>20190830</startDate>
          <endDate>20190930</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>FRIDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(updating FeeItems set with multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <placeholderType>QUICKLINK</placeholderType>
        <operand>
          <feedItemId>200000002</feedItemId>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_TEXT</placeholderField>
            <feedAttributeValue>update quicklink feedItem.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_URL</placeholderField>
            <feedAttributeValue>http://www2.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="MultipleFeedItemAttribute">
            <placeholderField>ADDITIONAL_ADVANCED_URLS</placeholderField>
            <feedAttributeValues>
              <feedAttributeValue>http://www2.yahoo.co.jp/lp1/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://www2.yahoo.co.jp/lp2/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://www2.yahoo.co.jp/lp3/</feedAttributeValue>
            </feedAttributeValues>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>ADVANCED_MOBILE_URL</placeholderField>
            <feedAttributeValue>http://mobile.mobile.yahoo.co.jp</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="MultipleFeedItemAttribute">
            <placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</placeholderField>
            <feedAttributeValues>
              <feedAttributeValue>http://mobile.yahoo.co.jp/lp1/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://mobile.yahoo.co.jp/lp2/</feedAttributeValue>
            </feedAttributeValues>
            <feedAttributeValues>
              <feedAttributeValue>http://mobile.yahoo.co.jp/lp3/</feedAttributeValue>
            </feedAttributeValues>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>TRACKING_URL</placeholderField>
            <feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site2}&amp;pid={_id3}&amp;vid={_id4}</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 1.</feedAttributeValue>
          </feedItemAttribute>
          <feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="SimpleFeedItemAttribute">
            <placeholderField>LINK_DESCRIPTION_1</placeholderField>
            <feedAttributeValue>link description 2.</feedAttributeValue>
          </feedItemAttribute>
          <startDate>20190831</startDate>
          <endDate>20191001</endDate>
          <scheduling>
            <schedules>
              <dayOfWeek>FRIDAY</dayOfWeek>
              <startHour>14</startHour>
              <startMinute>ZERO</startMinute>
              <endHour>15</endHour>
              <endMinute>FIFTEEN</endMinute>
            </schedules>
          </scheduling>
          <customParameters>
            <parameters>
              <key>site2</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id3</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id4</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Set Feed Item information.

| Parameter | Data Type |
| -------- | ------- |
| rval | [FeedItemReturnValue](../data/FeedItem/FeedItemReturnValue.md) |

##### Response Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423287</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>quicklink feedItem.</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>update quicklink feedItem.</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://mobile.mobile.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site2}&amp;pid={_id3}&amp;vid={_id4}</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site2</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id3</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id4</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Call Extensions)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423301</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000003</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALL_PHONE_NUMBER</ns2:placeholderField>
              <ns2:feedAttributeValue>0120-111-222</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>0120-888-999</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLEXTENSION</ns2:placeholderType>
            <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Ad Customizer)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423317</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>300000001</ns2:feedFolderId>
            <ns2:feedItemId>200000005</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>set test</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>20171231 235959</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>9012345678</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>8,888,888.88</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:targetingKeyword>
              <ns2:targetingKeywordId>600000002</ns2:targetingKeywordId>
              <ns2:text>set test keyword</ns2:text>
              <ns2:matchType>EXACT</ns2:matchType>
            </ns2:targetingKeyword>
            <ns2:geoTargeting>
              <ns2:targetId>JP-01-0011</ns2:targetId>
              <ns2:type>LOCATION</ns2:type>
              <ns2:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Callout option)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423331</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000004</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALLOUT_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>callout text.</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>set callout text.</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLOUT</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Category Text)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423345</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_HEADER</ns2:placeholderField>
              <ns2:feedAttributeValue>ブランド</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>ブランド</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_VALUES</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>NIKE</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>FILA</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>ADIDAS</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>ASICS</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>PUMA</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>CHAMPION</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>STRUCTURED_SNIPPET</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(updating FeeItems set with multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423360</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000002</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>quicklink feedItem.</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>update quicklink feedItem.</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://mobile.mobile.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site2}&amp;pid={_id3}&amp;vid={_id4}</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp/lp1/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp/lp2/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp/lp3/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://mobile.yahoo.co.jp/lp1/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://mobile.yahoo.co.jp/lp2/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://mobile.yahoo.co.jp/lp3/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site2</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id3</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id4</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request

Remove Feed Item information.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [FeedItemOperation](../data/FeedItem/FeedItemOperation.md) |

##### Request Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <placeholderType>QUICKLINK</placeholderType>
        <operand>
          <feedItemId>200000001</feedItemId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Call Extensions)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <placeholderType>CALLEXTENSION</placeholderType>
        <operand>
          <feedItemId>200000003</feedItemId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Ad Customizer)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <placeholderType>AD_CUSTOMIZER</placeholderType>
        <operand>
          <feedItemId>200000005</feedItemId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Callout option)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <placeholderType>CALLOUT</placeholderType>
        <operand>
          <feedItemId>200000004</feedItemId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(Category Text)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <placeholderType>STRUCTURED_SNIPPET</placeholderType>
        <operand>
          <feedItemId>200000001</feedItemId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample(QuickLinks, including removing multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <placeholderType>QUICKLINK</placeholderType>
        <operand>
          <feedItemId>200000002</feedItemId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Remove Feed Item information.

| Parameter | Data Type |
| -------- | ------- |
| rval | [FeedItemReturnValue](../data/FeedItem/FeedItemReturnValue.md) |

##### Response Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423376</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>quicklink feedItem.</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>update quicklink feedItem.</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://mobile.mobile.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site2}&amp;pid={_id3}&amp;vid={_id4}</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site2</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id3</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id4</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Call Extensions)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423391</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000003</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALL_PHONE_NUMBER</ns2:placeholderField>
              <ns2:feedAttributeValue>0120-111-222</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>0120-888-999</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLEXTENSION</ns2:placeholderType>
            <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Ad Customizer)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423408</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>300000001</ns2:feedFolderId>
            <ns2:feedItemId>200000005</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>set test</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>20171231 235959</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>9012345678</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:reviewFeedAttributeValue>8,888,888.88</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:targetingKeyword>
              <ns2:targetingKeywordId>600000002</ns2:targetingKeywordId>
              <ns2:text>set test keyword</ns2:text>
              <ns2:matchType>EXACT</ns2:matchType>
            </ns2:targetingKeyword>
            <ns2:geoTargeting>
              <ns2:targetId>JP-01-0011</ns2:targetId>
              <ns2:type>LOCATION</ns2:type>
              <ns2:geoTargetingRestriction>LOCATION_OF_PRESENCE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Callout option)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423428</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000004</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>CALLOUT_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>callout text.</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>set callout text.</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>CALLOUT</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(Category Text)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423446</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_HEADER</ns2:placeholderField>
              <ns2:feedAttributeValue>ブランド</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>ブランド</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>STRUCTURED_SNIPPET_VALUES</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>NIKE</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>FILA</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>ADIDAS</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>ASICS</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>PUMA</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>CHAMPION</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>STRUCTURED_SNIPPET</ns2:placeholderType>
            <ns2:startDate>20190830</ns2:startDate>
            <ns2:endDate>20190930</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample(QuickLinks, including removing multiple Landing Page URLs)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423461</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000002</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>quicklink feedItem.</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>update quicklink feedItem.</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://mobile.mobile.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site2}&amp;pid={_id3}&amp;vid={_id4}</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp/lp1/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp/lp2/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://www.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp/lp3/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:MultipleFeedItemAttribute">
              <ns2:placeholderField>ADDITIONAL_ADVANCED_MOBILE_URLS</ns2:placeholderField>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp1/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://mobile.yahoo.co.jp/lp1/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp2/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://mobile.yahoo.co.jp/lp2/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
              <ns2:feedAttributeValues>
                <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp/lp3/</ns2:feedAttributeValue>
                <ns2:reviewFeedAttributeValue>http://mobile.yahoo.co.jp/lp3/</ns2:reviewFeedAttributeValue>
              </ns2:feedAttributeValues>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site2</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id3</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id4</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## setTrademarkStatus

### Request

Confirm the status of trademark restriction.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [FeedItemSetTrademarkStatusOperation](../data/FeedItem/FeedItemSetTrademarkStatusOperation.md) |

##### Request Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <setTrademarkStatus xmlns="http://ss.yahooapis.jp/V201909/FeedItem">
      <operations>
        <accountId>100000001</accountId>
        <placeholderType>QUICKLINK</placeholderType>
        <operand>
          <feedItemId>200000001</feedItemId>
        </operand>
      </operations>
    </setTrademarkStatus>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

Confirm the status of trademark restriction.

| Parameter | Data Type |
| -------- | ------- |
| rval | [FeedItemReturnValue](../data/FeedItem/FeedItemReturnValue.md) |

##### Response Sample(QuickLinks)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1567167423475</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:setTrademarkStatusResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedItemId>200000001</ns2:feedItemId>
            <ns2:feedItemTrackId>0</ns2:feedItemTrackId>
            <ns2:approvalStatus>APPROVED_WITH_REVIEW</ns2:approvalStatus>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_TEXT</ns2:placeholderField>
              <ns2:feedAttributeValue>quicklink feedItem.</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>update quicklink feedItem.</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://www.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://www2.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>ADVANCED_MOBILE_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://mobile.mobile.yahoo.co.jp</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>TRACKING_URL</ns2:placeholderField>
              <ns2:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:feedAttributeValue>
              <ns2:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site2}&amp;pid={_id3}&amp;vid={_id4}</ns2:reviewFeedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 1.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:feedItemAttribute xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SimpleFeedItemAttribute">
              <ns2:placeholderField>LINK_DESCRIPTION_1</ns2:placeholderField>
              <ns2:feedAttributeValue>link description 2.</ns2:feedAttributeValue>
            </ns2:feedItemAttribute>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:startDate>20190831</ns2:startDate>
            <ns2:endDate>20191001</ns2:endDate>
            <ns2:scheduling>
              <ns2:schedules>
                <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
                <ns2:startHour>14</ns2:startHour>
                <ns2:startMinute>ZERO</ns2:startMinute>
                <ns2:endHour>15</ns2:endHour>
                <ns2:endMinute>FIFTEEN</ns2:endMinute>
              </ns2:schedules>
            </ns2:scheduling>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:reviewCustomParameters>
              <ns2:parameters>
                <ns2:key>site2</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id3</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id4</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:reviewCustomParameters>
            <ns2:geoTargeting>
              <ns2:geoTargetingRestriction>NONE</ns2:geoTargetingRestriction>
            </ns2:geoTargeting>
          </ns2:feedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:setTrademarkStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
