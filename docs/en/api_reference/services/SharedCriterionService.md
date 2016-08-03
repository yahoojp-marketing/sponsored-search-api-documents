# SharedCriterionService
Use this service to add or remove negative keyword to negative keyword list.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/SharedCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/SharedCriterionService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Use this service to add or remove negative keywords to negative keyword list.
Up to 5,000 negative keywords can be added per list.

#### Operation
Describes operation provided by SharedCriterionService.

## get
Get negative keyword list information.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [SharedCriterionSelector](../data/SharedCriterionSelector.md) | Object to hold search criteria (exec parameter) of get method. | 

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
           <ns1:criterionIds>500</ns1:criterionIds>
           <ns1:criterionIds>501</ns1:criterionIds>
            <ns1:paging>
               <ns1:startIndex>500</ns1:startIndex>
               <ns1:numberResults>2</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [SharedCriterionPage](../data/SharedCriterionPage.md) | Object to hold exec result (all entities list) of get method. | 


##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
        <ns1:service>SharedCriterionService</ns1:service>
        <ns1:remainingQuota>-1</ns1:remainingQuota>
        <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
        <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getResponse>
        <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
           <ns1:Page.Type>SharedCriterionPage</ns1:Page.Type>
           <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:sharedCriterion>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:criterionId>501</ns1:criterionId>
                  <ns1:text>Sample Keyword</ns1:text>
                  <ns1:matchType>EXACT</ns1:matchType>
                  <ns1:criterionUseType>NEGATIVE</ns1:criterionUseType>
               </ns1:sharedCriterion>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:sharedCriterion>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:criterionId>500</ns1:criterionId>
                  <ns1:text>Sample Keyword</ns1:text>
                  <ns1:matchType>PHRASE</ns1:matchType>
                  <ns1:criterionUseType>NEGATIVE</ns1:criterionUseType>
               </ns1:sharedCriterion>
            </ns1:values>
         </ns1:rval>
     </ns1:getResponse>
   </soapenv:Body>
</soapenv:Envelope>
```


## mutate(ADD)
Add negative keywords to negative keyword list.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [SharedCriterionOperation](../data/SharedCriterionOperation.md) | Object to hold negative keyword list for operation of mutate method.| 

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
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:text>Sample Keyword</ns1:text>
               <ns1:matchType>PHRASE</ns1:matchType>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:text>Sample Keyword</ns1:text>
               <ns1:matchType>EXACT</ns1:matchType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [SharedCriterionReturnValue](../data/SharedCriterionReturnValue.md) | Object to hold exec result (all entities list) of mutate method. | 


#### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>SharedCriterionService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>SharedCriterionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:sharedCriterion>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:criterionId>500</ns1:criterionId>
                  <ns1:text>Sample Keyword</ns1:text>
                  <ns1:matchType>PHRASE</ns1:matchType>
                  <ns1:criterionUseType>NEGATIVE</ns1:criterionUseType>
               </ns1:sharedCriterion>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:sharedCriterion>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:criterionId>501</ns1:criterionId>
                  <ns1:text>Sample Keyword</ns1:text>
                  <ns1:matchType>EXACT</ns1:matchType>
                  <ns1:criterionUseType>NEGATIVE</ns1:criterionUseType>
               </ns1:sharedCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```
## mutate(REMOVE)
Removes negative keywords from negative keyword list.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [SharedCriterionOperation](../data/SharedCriterionOperation.md) | Object to hold negative keyword list for operation of mutate method.| 

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
               <ns1:criterionId>500</ns1:criterionId>
           </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:criterionId>501</ns1:criterionId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [SharedCriterionReturnValue](../data/SharedCriterionReturnValue.md) | Object to hold exec result (all entities list) of mutate method. | 


#### Response Sample
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
        <ns1:service>SharedCriterionService</ns1:service>
        <ns1:remainingQuota>-1</ns1:remainingQuota>
        <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
        <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
        <ns1:rval>
            <ns1:ListReturnValue.Type>SharedCriterionReturnValue</ns1:ListReturnValue.Type>
           <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:sharedCriterion>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:criterionId>500</ns1:criterionId>
                  <ns1:text>Sample Keyword</ns1:text>
                  <ns1:matchType>PHRASE</ns1:matchType>
                  <ns1:criterionUseType>NEGATIVE</ns1:criterionUseType>
               </ns1:sharedCriterion>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:sharedCriterion>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:criterionId>501</ns1:criterionId>
                  <ns1:text>Sample Keyword</ns1:text>
                  <ns1:matchType>EXACT</ns1:matchType>
                  <ns1:criterionUseType>NEGATIVE</ns1:criterionUseType>
               </ns1:sharedCriterion>
            </ns1:values>
        </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
