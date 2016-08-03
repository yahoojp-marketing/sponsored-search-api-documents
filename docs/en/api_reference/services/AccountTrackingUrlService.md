# AccountTrackingUrlService
AccountTrackingUrlService is to get or update accoutn tracking information.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AccountTrackingUrlService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AccountTrackingUrlService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Get or update account tracking.

#### Operation
Describe the operation which provides at AccountTrackingUrlService.

## get
Retrieves information related to account tracking.

#### Request
| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [AccountTrackingUrlSelector](../data/AccountTrackingUrlSelector.md) |  Account tracking information relate to the operations to apply.| 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
      <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountIds>100000001</ns1:accountIds>
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>20</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [AccountTrackingUrlPage](../data/AccountTrackingUrlPage.md) | The acquired entry related account tracking. | 

##### Response Fields
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AccountTrackingUrlService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>AccountTrackingUrlPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:accountTrackingUrl>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
            <ns1:trackingUrl>>http://www.xxxxx.com/?url={lpurl}&amp;id=1</ns1:trackingUrl>
            <ns1:inReviewUrl>>http://www.xxxxx.com/?url={lpurl}&amp;id=2</ns1:inReviewUrl>
            <ns1:disapprovalReviewUrl>>http://www.xxxxx.com/?url={lpurl}&amp;id=3</ns1:disapprovalReviewUrl>
            <ns1:urlApprovalStatus>DISAPPROVED</ns1:urlApprovalStatus>
            <ns1:disapprovalReasonCodes>1001</ns1:disapprovalReasonCodes>
            <ns1:disapprovalReasonCodes>1002</ns1:disapprovalReasonCodes>
          </ns1:accountTrackingUrl>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:accountTrackingUrl>
            <ns1:accountId>100000002</ns1:accountId>
            <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
            <ns1:trackingUrl>>http://www.xxxxx.com/?url={lpurl}&amp;id=1</ns1:trackingUrl>
            <ns1:inReviewUrl>>http://www.xxxxx.com/?url={lpurl}&amp;id=2</ns1:inReviewUrl>
            <ns1:disapprovalReviewUrl>>http://www.xxxxx.com/?url={lpurl}&amp;id=3</ns1:disapprovalReviewUrl>
            <ns1:urlApprovalStatus>DISAPPROVED</ns1:urlApprovalStatus>
            <ns1:disapprovalReasonCodes>1001</ns1:disapprovalReasonCodes>
            <ns1:disapprovalReasonCodes>1002</ns1:disapprovalReasonCodes>
          </ns1:accountTrackingUrl>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Updates account tracking information.

#### Request
| Field | Restrictions | Data Type | DEscription | 
|---|---|---|---|
| operations | ○ | [AccountTrackingUrlOperation](../data/AccountTrackingUrlOperation.md) | Operation elements for account tracking information. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
      <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>SET</ns1:operator>
        <ns1:operand>
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:trackingUrl>http://www.xxxxx.com/?url={lpurl}&amp;id=2</ns1:trackingUrl>
        </ns1:operand>
<!-- When deleting the trackingUrl setting -->
        <ns1:operand>
          <ns1:accountId>100000002</ns1:accountId>
          <ns1:trackingUrl></ns1:trackingUrl>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [AccountTrackingUrlReturnValue](../data/AccountTrackingUrlReturnValue.md) | Container for account tracking information including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AccountTrackingUrlService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AccountTrackingUrlReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:accountTrackingUrl>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
            <ns1:trackingUrl>http://www.xxxxx.com/?url={lpurl}&amp;id=1</ns1:trackingUrl>
            <ns1:inReviewUrl>http://www.xxxxx.com/?url={lpurl}&amp;id=2</ns1:inReviewUrl>
            <ns1:urlApprovalStatus>APPROVED_WITH_REVIEW</ns1:urlApprovalStatus>
          </ns1:accountTrackingUrl>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:accountTrackingUrl>
            <ns1:accountId>100000002</ns1:accountId>
            <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
          </ns1:accountTrackingUrl>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
