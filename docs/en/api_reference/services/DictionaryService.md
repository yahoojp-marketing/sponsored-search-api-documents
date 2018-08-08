# DictionaryService
DictionaryService is to get EditorialReason and location information list.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/DictionaryService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/DictionaryService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201808/Dictionary
#### Overview
Get EditorialReason list
#### Operation
Descrives the operation provided by DictionaryService

+ [getDisapprovalReason](#getdisapprovalreason)
+ [getGeographicLocation](#getgeographiclocation)

#### Object
[Dictionary](../data/Dictionary)

## getDisapprovalReason

### Request
Get EditorialReason and recommended resolution list.

| Parameter | Restrictions | Data type | Description |
|---|---|---|---|
| selector | Required | [DisapprovalReasonSelector](../data/Dictionary/DisapprovalReasonSelector.md) | Specify langage in the EditorialReason list |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/Dictionary" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getDisapprovalReason xmlns="http://ss.yahooapis.jp/V201808/Dictionary">
      <selector>
        <lang>EN</lang>
      </selector>
    </getDisapprovalReason>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [DisapprovalPage](../data/Dictionary/DisapprovalPage.md) | EditorialReason list |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/Dictionary" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1523506333356</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getDisapprovalReasonResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Dictionary">
      <ns2:rval>
        <totalNumEntries>3</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:disapprovalReason>
            <ns2:disapprovalReasonCode>1</ns2:disapprovalReasonCode>
            <ns2:lang>EN</ns2:lang>
            <ns2:title>sample title.</ns2:title>
            <ns2:description>sample description.</ns2:description>
          </ns2:disapprovalReason>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:disapprovalReason>
            <ns2:disapprovalReasonCode>2</ns2:disapprovalReasonCode>
            <ns2:lang>EN</ns2:lang>
            <ns2:title>sample title.</ns2:title>
            <ns2:description>sample description.</ns2:description>
          </ns2:disapprovalReason>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:disapprovalReason>
            <ns2:disapprovalReasonCode>3</ns2:disapprovalReasonCode>
            <ns2:lang>EN</ns2:lang>
            <ns2:title>sample title.</ns2:title>
            <ns2:description>sample description.</ns2:description>
          </ns2:disapprovalReason>
        </ns2:values>
      </ns2:rval>
    </ns2:getDisapprovalReasonResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getGeographicLocation

### Request
Get the information list of geo targeting.

| Parameter | Requirement | Data type | Description |
|---|---|---|---|
| selector | Req | [GeographicLocationSelector](../data/Dictionary/GeographicLocationSelector.md) | Specify langage in the location information list. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/Dictionary" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getGeographicLocation xmlns="http://ss.yahooapis.jp/V201808/Dictionary">
      <selector>
        <lang>EN</lang>
      </selector>
    </getGeographicLocation>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [GeographicLocationPage](../data/Dictionary/GeographicLocationPage.md) | List of geo targeting information. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/Dictionary" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>Dictionary</ns2:service>
      <ns2:requestTime>1523506333370</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getGeographicLocationResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Dictionary">
      <ns2:rval>
        <totalNumEntries>47</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:geographicLocation>
            <ns2:code>JP-01</ns2:code>
            <ns2:name>Hokkaido</ns2:name>
            <ns2:fullName>Hokkaido</ns2:fullName>
            <ns2:order>0000000000</ns2:order>
            <ns2:status>ACTIVE</ns2:status>
            <ns2:child>
              <ns2:code>JP-01-0003</ns2:code>
              <ns2:parent>JP-01</ns2:parent>
              <ns2:name>Asahikawa</ns2:name>
              <ns2:fullName>Asahikawa,Hokkaido</ns2:fullName>
              <ns2:order>0000000100</ns2:order>
              <ns2:status>ACTIVE</ns2:status>
            </ns2:child>
            <ns2:child>
              <ns2:code>JP-01-0005</ns2:code>
              <ns2:parent>JP-01</ns2:parent>
              <ns2:name>Ashibetsu</ns2:name>
              <ns2:fullName>Ashibetsu,Hokkaido</ns2:fullName>
              <ns2:order>0000000200</ns2:order>
              <ns2:status>ACTIVE</ns2:status>
            </ns2:child>
            <ns2:child>
              <ns2:code>JP-01-0004</ns2:code>
              <ns2:parent>JP-01</ns2:parent>
              <ns2:name>Ashoro</ns2:name>
              <ns2:fullName>Ashoro,Hokkaido</ns2:fullName>
              <ns2:order>0000000300</ns2:order>
              <ns2:status>ACTIVE</ns2:status>
            </ns2:child>
          </ns2:geographicLocation>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:geographicLocation>
            <ns2:code>JP-02</ns2:code>
            <ns2:name>Aomori</ns2:name>
            <ns2:fullName>Aomori</ns2:fullName>
            <ns2:order>0100000000</ns2:order>
            <ns2:status>ACTIVE</ns2:status>
            <ns2:child>
              <ns2:code>JP-02-0002</ns2:code>
              <ns2:parent>JP-02</ns2:parent>
              <ns2:name>Aomori</ns2:name>
              <ns2:fullName>Aomori,Aomori</ns2:fullName>
              <ns2:order>0100000100</ns2:order>
              <ns2:status>ACTIVE</ns2:status>
            </ns2:child>
            <ns2:child>
              <ns2:code>JP-02-0001</ns2:code>
              <ns2:parent>JP-02</ns2:parent>
              <ns2:name>Ajigasawa</ns2:name>
              <ns2:fullName>Ajigasawa,Aomori</ns2:fullName>
              <ns2:order>0100000200</ns2:order>
              <ns2:status>ACTIVE</ns2:status>
            </ns2:child>
          </ns2:geographicLocation>
        </ns2:values>
      </ns2:rval>
    </ns2:getGeographicLocationResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
