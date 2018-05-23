# AccountSharedService
Use this service to get, add, update or remove ad information of negative keyword list which can be shared within the account.


#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/AccountSharedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/AccountSharedService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201805/AccountShared

#### Overview
Use this service to get, add, update and remove negative keyword list.
Up to 20 negative keyword lists per account can be added.
For On-Behalf-Of Account, only the accountId specified with Soap header can do "get" operation.

#### Operation
Describes operation provided by AccountSharedService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[AccountShared](../data/AccountShared)

## get
Get negative keyword list information.

### Request
| Parameter  | Requirement | Data Type | Description |
|---|---|---|---|
| selector | Req | [AccountSharedSelector](../data/AccountShared/AccountSharedSelector.md) | Object to hold search criteria (exec parameter) of get method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>111111</accountId>
        <sharedListIds>22</sharedListIds>
        <sharedListIds>33</sharedListIds>
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
| Field | Data type | Description |
|---|---|---|
| rval | [AccountSharedPage](../data/AccountShared/AccountSharedPage.md) | Object to hold exec result (all entities list) of get method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506327096</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_UpdatedOn_20180412</ns2:name>
            <ns2:memberCount>1</ns2:memberCount>
            <ns2:referenceCount>1</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Add negative keyword list to account.

### Request
| Parameter  | Requirement | Data Type | Description |
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountShared/AccountSharedOperation.md) | Object to hold campaign for operation of mutate method.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AccountShared">
      <operations>
        <operator>ADD</operator>
        <accountId>1111</accountId>
        <operand>
          <name>sample</name>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data type | Description |
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountShared/AccountSharedReturnValue.md)| Object to hold exec result (all entities list) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506327124</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <ListReturnValue.Type>AccountSharedReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_CreatedOn_20180412</ns2:name>
            <ns2:referenceCount>0</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Update negative keyword list information of account.

### Request
| Parameter  | Requirement | Data Type | Description |
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountShared/AccountSharedOperation.md)|  Object to hold campaign for operation of mutate method.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AccountShared">
      <operations>
        <operator>SET</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>2222</sharedListId>
          <name>SampleSharedAccount_UpdatedOn_20180412</name>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data type | Description |
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountShared/AccountSharedReturnValue.md) | Object to hold exec result (all entities list) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506327156</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <ListReturnValue.Type>AccountSharedReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:sharedListId>2222</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_UpdatedOn_20180412</ns2:name>
            <ns2:memberCount>1</ns2:memberCount>
            <ns2:referenceCount>1</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove negative keyword list from account.

### Request
| Parameter  | Requirement | Data Type | Description |
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountShared/AccountSharedOperation.md) |  Object to hold campaign for operation of mutate method.|

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AccountShared">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>2222</sharedListId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data type | Description |
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountShared/AccountSharedReturnValue.md) | Object to hold exec result (all entities list) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506327178</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <ListReturnValue.Type>AccountSharedReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:sharedListId>2222</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_UpdatedOn_20180412</ns2:name>
            <ns2:memberCount>1</ns2:memberCount>
            <ns2:referenceCount>1</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
