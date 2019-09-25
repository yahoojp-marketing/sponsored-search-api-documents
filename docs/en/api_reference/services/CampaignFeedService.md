# CampaignFeedService
CampaignFeedService is to get and update the FeedItem information of campaign.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/CampaignFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/CampaignFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201909/CampaignFeed
#### Overview
Use this service to get, add, update or remove the FeedItem information of campaign.
#### Operation
Describes the operation which provides by CampaignFeedService.
+ [get](#get)
+ [mutate(SET)](#mutateset)

#### Object
[CampaignFeed](../data/CampaignFeed)

## get
Get FeedItem information of campaign.

### Request

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [CampaignFeedSelector](../data/CampaignFeed/CampaignFeedSelector.md) | The FeedItem selector for operaions. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <feedItemIds>20001</feedItemIds>
        <feedItemIds>20002</feedItemIds>
        <feedItemIds>20003</feedItemIds>
        <feedItemIds>20004</feedItemIds>
        <feedItemIds>20005</feedItemIds>
        <placeholderTypes>QUICKLINK</placeholderTypes>
        <placeholderTypes>CALLEXTENSION</placeholderTypes>
        <placeholderTypes>CALLOUT</placeholderTypes>
        <placeholderTypes>STRUCTURED_SNIPPET</placeholderTypes>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>100</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Filed | Data Type | Description |
|---|---|---|
| rval | [CampaignFeedPage](../data/CampaignFeed/CampaignFeedPage.md) | This object is a container for selected FeedItem information. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignFeed</ns2:service>
      <ns2:requestTime>1547793122759</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignFeed">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>CampaignFeedPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:campaignFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:feedItemId>20001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:campaignFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:campaignFeedList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
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
| operations | Req | [CampaignFeedOperation](../data/CampaignFeed/CampaignFeedOperation.md) | Operation elements for FeedItem information of campaign. <br>FeedItem setting will be overwritten. To release FeedItem information, update the blank data. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/CampaignFeed">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <placeholderType>QUICKLINK</placeholderType>
          <campaignFeed>
            <feedItemId>20001</feedItemId>
          </campaignFeed>
          <devicePlatform>DESKTOP</devicePlatform>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [CampaignFeedReturnValue](../data/CampaignFeed/CampaignFeedReturnValue.md) | This object is a container for FeeItem information set on campaign which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignFeed</ns2:service>
      <ns2:requestTime>1547793122810</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignFeed">
      <ns2:rval>
        <ListReturnValue.Type>CampaignFeedReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:campaignFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:feedItemId>20001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:campaignFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:campaignFeedList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
