# SharedCriterionService
Use this service to add or remove negative keyword to negative keyword list.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/SharedCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/SharedCriterionService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201909/SharedCriterion

#### Overview
Use this service to add or remove negative keywords to negative keyword list.
Up to 5,000 negative keywords can be added per list.

#### Operation
Describes operation provided by SharedCriterionService.

 [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[SharedCriterion](../data/SharedCriterion)

## get
Get negative keyword list information.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [SharedCriterionSelector](../data/SharedCriterion/SharedCriterionSelector.md) | Object to hold search criteria (exec parameter) of get method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>1234567890</accountId>
        <sharedListIds>10001</sharedListIds>
        <sharedListIds>10002</sharedListIds>
        <sharedListIds>10003</sharedListIds>
        <sharedListIds>10004</sharedListIds>
        <sharedListIds>10005</sharedListIds>
        <criterionIds>20001</criterionIds>
        <criterionIds>20002</criterionIds>
        <criterionIds>20003</criterionIds>
        <criterionIds>20004</criterionIds>
        <criterionIds>20005</criterionIds>
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
| Field | Data Type | Description |
|---|---|---|
| rval | [SharedCriterionPage](../data/SharedCriterion/SharedCriterionPage.md) | Object to hold exec result (all entities list) of get method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>SharedCriterion</ns2:service>
      <ns2:requestTime>1547792810826</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/SharedCriterion">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>SharedCriterionPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:sharedCriterion>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:sharedListId>10001</ns2:sharedListId>
            <ns2:criterionId>20001</ns2:criterionId>
            <ns2:text>test keyword.</ns2:text>
            <ns2:matchType>PHRASE</ns2:matchType>
            <ns2:criterionUseType>NEGATIVE</ns2:criterionUseType>
          </ns2:sharedCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Add negative keywords to negative keyword list.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [SharedCriterionOperation](../data/SharedCriterion/SharedCriterionOperation.md) | Object to hold negative keyword list for operation of mutate method.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <sharedListId>10001</sharedListId>
          <text>test keyword.</text>
          <matchType>PHRASE</matchType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [SharedCriterionReturnValue](../data/SharedCriterion/SharedCriterionReturnValue.md) | Object to hold exec result (all entities list) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>SharedCriterion</ns2:service>
      <ns2:requestTime>1547792810882</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/SharedCriterion">
      <ns2:rval>
        <ListReturnValue.Type>SharedCriterionReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:sharedCriterion>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:sharedListId>10001</ns2:sharedListId>
            <ns2:criterionId>20001</ns2:criterionId>
            <ns2:text>test keyword.</ns2:text>
            <ns2:matchType>PHRASE</ns2:matchType>
            <ns2:criterionUseType>NEGATIVE</ns2:criterionUseType>
          </ns2:sharedCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Removes negative keywords from negative keyword list.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [SharedCriterionOperation](../data/SharedCriterion/SharedCriterionOperation.md) | Object to hold negative keyword list for operation of mutate method.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <sharedListId>10001</sharedListId>
          <criterionId>20001</criterionId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [SharedCriterionReturnValue](../data/SharedCriterion/SharedCriterionReturnValue.md) | Object to hold exec result (all entities list) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/SharedCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>SharedCriterion</ns2:service>
      <ns2:requestTime>1547792810961</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/SharedCriterion">
      <ns2:rval>
        <ListReturnValue.Type>SharedCriterionReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:sharedCriterion>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:sharedListId>10001</ns2:sharedListId>
            <ns2:criterionId>20001</ns2:criterionId>
            <ns2:text>test keyword.</ns2:text>
            <ns2:matchType>PHRASE</ns2:matchType>
            <ns2:criterionUseType>NEGATIVE</ns2:criterionUseType>
          </ns2:sharedCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
