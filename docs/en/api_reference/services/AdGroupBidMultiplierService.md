# AdGroupBidMultiplierService
Use this service to get or update bid multiplier information.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/AdGroupBidMultiplierService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/AdGroupBidMultiplierService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier
#### Overview
Use this service to get, update adgroup bid multiplier.
#### Operation
Explains the operation which provides at AdGroupBidMultiplierService.
+ [get](#get)
+ [mutate(SET)](#mutate-set)
+ [mutate(REMOVE)](#mutate-remove)


#### Object
[AdGroupBidMultiplier](../data/AdGroupBidMultiplier)

## get

#### Request
Gets bid multiplier of adgroup

| name | Req | Value | Description |
|---|---|---|---|
| selector | Req | [AdGroupBidMultiplierSelector](../data/AdGroupBidMultiplier/AdGroupBidMultiplierSelector.md) | Filters the adgroup bid multiplier to be returned. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201901">
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
        <platformTypes>DESKTOP</platformTypes>
        <platformTypes>TABLET</platformTypes>
        <platformTypes>SMART_PHONE</platformTypes>
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
| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupBidMultiplierPage](../data/AdGroupBidMultiplier/AdGroupBidMultiplierPage.md) | A page (subset) view of the ad group bit multiplier selected. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupBidMultiplier</ns2:service>
      <ns2:requestTime>1547793791788</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupBidMultiplierPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupBidMultiplier>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:platformType>DESKTOP</ns2:platformType>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:adGroupBidMultiplier>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Updates adgroup bid multiplier.

### Request
| Name | Req | Value | Description |
|---|---|---|---|
| operations | Req | [AdGroupBidMultiplierOperation](../data/AdGroupBidMultiplier/AdGroupBidMultiplierOperation.md) | Bid multiplier and operation details of the ad group to be processed. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <platformType>DESKTOP</platformType>
          <bidMultiplier>10.0</bidMultiplier>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupBidMultiplierReturnValue](../data/AdGroupBidMultiplier/AdGroupBidMultiplierReturnValue.md) | Container of ad group bid multiplier information including return value. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupBidMultiplier</ns2:service>
      <ns2:requestTime>1547793791801</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupBidMultiplierReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupBidMultiplier>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:platformType>DESKTOP</ns2:platformType>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:adGroupBidMultiplier>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove bid multiplier which already set to ad group.

#### Request
| Parameter | Req | Valuer | Desecription |
|---|---|---|---|
| operations | Req | [AdGroupBidMultiplierOperation](../data/AdGroupBidMultiplier/AdGroupBidMultiplierOperation.md) | Bid multiplier and operation detail of ad group to be processed. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <platformType>DESKTOP</platformType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupBidMultiplierReturnValue](../data/AdGroupBidMultiplier/AdGroupBidMultiplierReturnValue.md) | Container for ad group bid multiplier including return value on operation. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupBidMultiplier</ns2:service>
      <ns2:requestTime>1547793791813</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupBidMultiplier">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupBidMultiplierReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupBidMultiplier>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:platformType>DESKTOP</ns2:platformType>
          </ns2:adGroupBidMultiplier>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
