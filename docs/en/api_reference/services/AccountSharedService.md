# AccountSharedService
Use this service to get, add, update or remove ad information of negative keyword list which can be shared within the account.


#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AccountSharedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AccountSharedService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Use this service to get, add, update and remove negative keyword list.
Up to 20 negative keyword lists per account can be added.
For On-Behalf-Of Account, only the accountId specified with Soap header can do "get" operation.

#### Operation
Describes operation provided by AccountSharedService.
<br>

## get
Get negative keyword list information.

### Request
| Parameter  | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | Req | [AccountSharedSelector](../data/AccountSharedSelector.md) | Object to hold search criteria (exec parameter) of get method. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
     </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:sharedListIds>1000</ns1:sharedListIds>
            <ns1:sharedListIds>1001</ns1:sharedListIds>
            <ns1:sharedListIds>1002</ns1:sharedListIds>
            <ns1:paging>
               <ns1:startIndex>10</ns1:startIndex>
               <ns1:numberResults>3</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data type | Description | 
|---|---|---|
| rval | [AccountSharedPage](../data/AccountSharedPage.md) | Object to hold exec result (all entities list) of get method. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>AccountSharedService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>AccountSharedPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:name>Sample Shared List 1000</ns1:name>
                  <ns1:memberCount>2000</ns1:memberCount>
                  <ns1:referenceCount>3</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:name>Sample Shared List 1001</ns1:name>
                  <ns1:memberCount>0</ns1:memberCount>
                  <ns1:referenceCount>0</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(ADD)
Add negative keyword list to account.

### Request
| Parameter  | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountSharedOperation.md) | Object to hold campaign for operation of mutate method.| 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:name>Sample Shared List No1</ns1:name>
            </ns1:operand>
            <ns1:operand>
               <ns1:name>Sample Shared List No2</ns1:name>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data type | Description | 
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountSharedReturnValue.md)| Object to hold exec result (all entities list) of mutate method. | 

#### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>AccountSharedService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AccountSharedReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:name>Sample Shared List No1</ns1:name>
                  <ns1:memberCount>0</ns1:memberCount>
                  <ns1:referenceCount>0</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:name>Sample Shared List No2</ns1:name>
                  <ns1:memberCount>0</ns1:memberCount>
                  <ns1:referenceCount>0</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(SET)
Update negative keyword list information of account.

### Request
| Parameter  | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountSharedOperation.md)|  Object to hold campaign for operation of mutate method.| 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:name>modify Sample Shared List No1</ns1:name>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:name>modify Sample Shared List No2</ns1:name>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data type | Description | 
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountSharedReturnValue.md) | Object to hold exec result (all entities list) of mutate method. | 

#### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>AccountSharedService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AccountSharedReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:name>modify Sample Shared List No1</ns1:name>
                  <ns1:memberCount>1000</ns1:memberCount>
                  <ns1:referenceCount>0</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:name>modify Sample Shared List No2</ns1:name>
                  <ns1:memberCount>200</ns1:memberCount>
                  <ns1:referenceCount>1</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(REMOVE)
Remove negative keyword list from account.

### Request
| Parameter  | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountSharedOperation.md) |  Object to hold campaign for operation of mutate method.| 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>REMOVE</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data type | Description | 
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountSharedReturnValue.md) | Object to hold exec result (all entities list) of mutate method. | 

#### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>AccountSharedService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AccountSharedReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:name>modify Sample Shared List No1</ns1:name>
                  <ns1:memberCount>1000</ns1:memberCount>
                  <ns1:referenceCount>0</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountShared>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:name>modify Sample Shared List No2</ns1:name>
                  <ns1:memberCount>200</ns1:memberCount>
                  <ns1:referenceCount>0</ns1:referenceCount>
               </ns1:accountShared>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

