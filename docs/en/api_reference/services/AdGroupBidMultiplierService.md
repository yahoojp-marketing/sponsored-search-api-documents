# AdGroupBidMultiplierService
Use this service to get or update bid multiplier information.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupBidMultiplierService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupBidMultiplierService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Overview
Use this service to get, update adgroup bid multiplier.
#### Operation
Explains the operation which provides at AdGroupBidMultiplierService.
## get
#### Request
Gets bid multiplier of adgroup

| name | Req | Value | Description | 
|---|---|---|---|
| selector | Req | [AdGroupBidMultiplierSelector](../data/AdGroupBidMultiplierSelector.md) | Filters the adgroup bid multiplier to be returned. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:campaignIds>100000004</ns1:campaignIds>
                <ns1:adGroupIds>100000005</ns1:adGroupIds>
                <ns1:adGroupIds>100000006</ns1:adGroupIds>
                <ns1:platformTypes>DESKTOP</ns1:platformTypes>
                <ns1:platformTypes>TABLET</ns1:platformTypes>
                <ns1:platformTypes>SMART_PHONE</ns1:platformTypes>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```



### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupBidMultiplierPage](../data/AdGroupBidMultiplierPage.md) | A page (subset) view of the ad group bit multiplier selected. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupBidMultiplierService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>6</ns1:totalNumEntries>
                <ns1:Page.Type>AdGroupBidMultiplierPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>SMART_PHONE</ns1:platformType>
                        <ns1:bidMultiplier>0.10</ns1:bidMultiplier>
                   </ns1:adGroupBidMultiplier>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>TABLET</ns1:platformType>
                        <ns1:bidMultiplier>0.50</ns1:bidMultiplier>
                   </ns1:adGroupBidMultiplier>
                </ns1:values>               
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000006</ns1:adGroupId>
                        <ns1:platformType>SMART_PHONE</ns1:platformType>
                        <ns1:bidMultiplier>2</ns1:bidMultiplier>
                   </ns1:adGroupBidMultiplier>
                </ns1:values>
                 <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000006</ns1:adGroupId>
                        <ns1:platformType>DESKTOP</ns1:platformType>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                  </ns1:adGroupBidMultiplier>
                </ns1:values>              
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>  
```
## mutate (SET)
### Request
Updates adgroup bid multiplier.

| Name | Req | Value | Description | 
|---|---|---|---|
| operations | Req | [AdGroupBidMultiplierOperation](../data/AdGroupBidMultiplierOperation.md) | Modify bid multiplier and operation details of the ad group to be processed. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000003</ns1:campaignId>                  
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                  
                    <ns1:platformType>SMART_PHONE</ns1:platformType>
                    <ns1:bidMultiplier>3.0</ns1:bidMultiplier>
               </ns1:operand>
                <ns1:operand>
                    <ns1:campaignId>1000000003</ns1:campaignId>                  
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                  
                    <ns1:platformType>TABLET</ns1:platformType>
                    <ns1:bidMultiplier>2.0</ns1:bidMultiplier>
               </ns1:operand>
                <ns1:operand>
                    <ns1:campaignId>1000000003</ns1:campaignId>                  
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                  
                    <ns1:platformType>DESKTOP</ns1:platformType>
                    <ns1:bidMultiplier>0</ns1:bidMultiplier>
               </ns1:operand>              
           </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupBidMultiplierReturnValue](../data/AdGroupBidMultiplierReturnValue.md) | Container of ad group bid multiplier information including return value. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupBidMultiplierService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupBidMultiplierReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>SMART_PHONE</ns1:platformType>
                         <ns1:bidMultiplier>3.0</ns1:bidMultiplier>                       
                    </ns1:adGroupBidMultiplier>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>TABLET</ns1:platformType>
                         <ns1:bidMultiplier>2.0</ns1:bidMultiplier>                       
                    </ns1:adGroupBidMultiplier>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>DESKTOP</ns1:platformType>
                         <ns1:bidMultiplier>0</ns1:bidMultiplier>                       
                    </ns1:adGroupBidMultiplier>
                </ns1:values>              
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(REMOVE)
Remove bid multiplier which already set to ad group.

#### Request
| Parameter | Req | Valuer | Desecription | 
|---|---|---|---|
| operations | Req | [AdGroupBidMultiplierOperation](../data/AdGroupBidMultiplierOperation.md) | Bid multiplier and operation detail of ad group to be processed. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000003</ns1:campaignId>                  
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                  
                    <ns1:platformType>SMART_PHONE</ns1:platformType>
              </ns1:operand>
                <ns1:operand>
                    <ns1:campaignId>1000000003</ns1:campaignId>                  
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                  
                    <ns1:platformType>TABLET</ns1:platformType>
               </ns1:operand>
                <ns1:operand>
                    <ns1:campaignId>1000000003</ns1:campaignId>                  
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                  
                    <ns1:platformType>DESKTOP</ns1:platformType>
               </ns1:operand>              
           </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupBidMultiplierReturnValue](../data/AdGroupBidMultiplierReturnValue.md) | Container for ad group bid multiplier including return value on operation. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupBidMultiplierService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupBidMultiplierReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>SMART_PHONE</ns1:platformType>
                   </ns1:adGroupBidMultiplier>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>TABLET</ns1:platformType>
                   </ns1:adGroupBidMultiplier>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:adGroupId>1000000005</ns1:adGroupId>
                        <ns1:platformType>DESKTOP</ns1:platformType>
                    </ns1:adGroupBidMultiplier>
                </ns1:values>              
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

