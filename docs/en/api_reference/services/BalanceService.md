# BalanceService
Use this service to retrieve account balance.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/BalanceService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/BalanceService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/Balance
#### Overview
Use this service to retrieve account balance.
#### Operation
Explains  the operation which provides at BalanceService.

+ [get](#get)

#### Object
[Balance](../data/Balance)

## get

### Request
Returns account balance.

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [BalanceSelector](../data/Balance/BalanceSelector.md) | The selector specifying the query. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Balance" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/Balance" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountIds>1111</accountIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type | Description |
|---|---|---|
| rval | [BalancePage](../data/Balance/BalancePage.md) | A page (subset) view of the balance selected. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Balance" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Balance</ns2:service>
      <ns2:requestTime>1523506330379</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Balance">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:balance>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:balance>10000</ns2:balance>
          </ns2:balance>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
