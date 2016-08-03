# CampaignSharedSetService
CampaignSharedSetService setup Negative keyword list to campaign.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Use this service to setup Negative keyword list to campaign.

#### Operation
Describe the operation which provides at CampaignSharedSetService.

## get
Returns the setup information between campaign and negative keyword list.

### Request
| Parameter | Restrictions| Data Type | Description | 
|---|---|---|---|
| selector | Req | [CampaignSharedSetSelector](../data/CampaignSharedSetSelector.md) | This is object which holds the search criteria (exec parameters) on get method. | 

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
            <ns1:campaignIds>100</ns1:campaignIds>
            <ns1:campaignIds>200</ns1:campaignIds>
            <ns1:campaignIds>300</ns1:campaignIds>
            <ns1:sharedListIds>1000</ns1:sharedListIds>
            <ns1:sharedListIds>1001</ns1:sharedListIds>
            <ns1:paging>
               <ns1:startIndex>4</ns1:startIndex>
               <ns1:numberResults>100</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignSharedSetPage](../data/CampaignSharedSetPage.md) | This is object which holds the exec result (List of all entities) of get method. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignSharedSetService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>CampaignSharedSetPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>300</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No3</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>200</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No2</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(ADD)
Setup negative keyword list for campaign.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignSharedSetOperation](../data/CampaignSharedSetOperation.md) | The object which holds setup information of campaign and negative keyword list for the operation by mutate method. | 

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
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>200</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:campaignId>300</ns1:campaignId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignSharedSetReturnValue](../data/CampaignSharedSetReturnValue.md) | This is object which holds the exec result (List of all entities) of mutate method. | 

#### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignSharedSetService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignSharedSetReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>200</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No2</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>300</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No3</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(REMOVE)
Remove the setup settings between campaign and negative keyword list.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignSharedSetOperation](../data/CampaignSharedSetOperation.md) |The object which holds setup information of campaign and negative keyword list for the operation by mutate method. | 

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
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>200</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:campaignId>300</ns1:campaignId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
Response field

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignSharedSetReturnValue](../data/CampaignSharedSetReturnValue.md) |This is object which holds the exec result (List of all entities) of mutate method. | 

#### Response Sample
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignSharedSetService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignSharedSetReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>200</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No2</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>300</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No3</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
