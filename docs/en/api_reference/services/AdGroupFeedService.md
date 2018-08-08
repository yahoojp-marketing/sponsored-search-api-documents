# AdGroupFeedService
AdGroupFeedService is to get, add, update or remove the FeedItem information of ad groups.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/AdGroupFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/AdGroupFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201808/AdGroupFeed
#### Overview
Use this service to get, add, update or remove the FeedItem information of ad groups.
#### Operation
Describes the operation which provides by AdGroupFeedService.

+ [get](#get)
+ [mutate(SET)](#mutateset)

#### Object
[AdGroupFeed](../data/AdgroupFeed)

## get
Returns FeedItem information of ad groups.

### Request

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [AdGroupFeedSelector](../data/AdGroupFeed/AdGroupFeedSelector.md) | The FeedItem selector for operaions. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <adGroupIds>20001</adGroupIds>
        <adGroupIds>20002</adGroupIds>
        <adGroupIds>20003</adGroupIds>
        <adGroupIds>20004</adGroupIds>
        <adGroupIds>20005</adGroupIds>
        <feedItemIds>30001</feedItemIds>
        <feedItemIds>30002</feedItemIds>
        <feedItemIds>30003</feedItemIds>
        <feedItemIds>30004</feedItemIds>
        <feedItemIds>30005</feedItemIds>
        <placeholderTypes>QUICKLINK</placeholderTypes>
        <placeholderTypes>CALLEXTENSION</placeholderTypes>
        <placeholderTypes>CALLOUT</placeholderTypes>
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
| rval | [AdGroupFeedPage](../data/AdGroupFeed/AdGroupFeedPage.md) | This object is a container for selected FeedItem information.<br>Cannot retrieve the ad group without FeedItem information. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupFeed</ns2:service>
      <ns2:requestTime>1523506329768</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupFeed">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupFeedPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:adGroupFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:adGroupId>20001</ns2:adGroupId>
              <ns2:feedItemId>30001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:adGroupFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:adGroupFeedList>
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
* It is not possible to set multiple FeedItem information to an adGroupId by single request.<br>

### Request

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupFeedOperation](../data/AdGroupFeed/AdGroupFeedOperation.md) | Operation elements for FeedItem information of ad group.<br>FeedItem setting will be overwritten.<br>To release FeedItem information, update with blank data. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/AdGroupFeed">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <placeholderType>QUICKLINK</placeholderType>
          <adGroupFeed>
            <feedItemId>20001</feedItemId>
          </adGroupFeed>
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
| rval | [AdGroupFeedReturnValue](../data/AdGroupFeed/AdGroupFeedReturnValue.md) | This object is a container for FeeItem information set on ad group which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupFeed</ns2:service>
      <ns2:requestTime>1523506329793</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupFeed">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupFeedReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:adGroupFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:adGroupId>20001</ns2:adGroupId>
              <ns2:feedItemId>30001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:adGroupFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:adGroupFeedList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
