# BiddingStrategyService
Use this service to get, add, update, or delete auto bidding information.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.2/BiddingStrategyService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.2/BiddingStrategyService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Use this service to create, update and remove auto bidding information.
#### Operation
Describe the operation which provides at BiddingStrategyService.
## get
### Request
Returns auto bidding information.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [BiddingStrategySelector](../data/BiddingStrategySelector.md) | This object is a container for auto bidding information. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
     <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:biddingStrategyIds>2222222222</ns1:biddingStrategyIds>
            <ns1:biddingStrategyIds>3333333333</ns1:biddingStrategyIds>
            <ns1:biddingStrategyIds>4444444444</ns1:biddingStrategyIds>
            <ns1:biddingStrategyIds>5555555555</ns1:biddingStrategyIds>
            <ns1:biddingStrategyIds>6666666666</ns1:biddingStrategyIds>
            <ns1:biddingStrategyTypes>PAGE_ONE_PROMOTED</ns1:biddingStrategyTypes>
            <ns1:biddingStrategyTypes>ENHANCED_CPC</ns1:biddingStrategyTypes>
            <ns1:biddingStrategyTypes>TARGET_CPA</ns1:biddingStrategyTypes>
            <ns1:biddingStrategyTypes>TARGET_ROAS</ns1:biddingStrategyTypes>
            <ns1:biddingStrategyTypes>TARGET_SPEND</ns1:biddingStrategyTypes>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>500</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```
### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [BiddingStrategyPage](../data/BiddingStrategyPage.md) | Container includes the information of Auto bidding. | 

###### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:Page.Type>AdGroupPage</ns1:Page.Type>
            <ns1:totalNumEntries>30</ns1:totalNumEntries>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroup>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000001</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>00000001</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:initialBid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>ADGROUP</ns1:bidSource>
                     </ns1:initialBid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
               </ns1:adGroup>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroup>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000001</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>00000002</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                        <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:initialBid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>ADGROUP</ns1:bidSource>
                     </ns1:initialBid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
               </ns1:adGroup>  
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroup>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000001</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>00000003</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 3</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:initialBid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>ADGROUP</ns1:bidSource>
                     </ns1:initialBid>
                  </ns1:biddingStrategyConfiguration>
               </ns1:adGroup>  
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
### Request
Creates the Auto bidding.

| Field | Req | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [BiddingStrategyOperation](../data/BiddingStrategyOperation.md) | Create the auto bidding settings. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1111111111</ns1:accountId>
            <!-- EnhancedCpcBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyName>ENHANCED_CPC_BiddingStartegy</ns1:biddingStrategyName>
               <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                  <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- PageOnePromotedBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyName>PAGE_ONE_PROMOTED_BiddingStartegy</ns1:biddingStrategyName>
               <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                  <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                  <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                  <ns1:bidCeiling>50000</ns1:bidCeiling>
                  <ns1:bidMultiplier>10.00</ns1:bidMultiplier>
                  <ns1:bidChangesForRaisesOnly>ACTIVE</ns1:bidChangesForRaisesOnly>
                  <ns1:raiseBidWhenBudgetConstrained>DEACTIVE</ns1:raiseBidWhenBudgetConstrained>
                  <ns1:raiseBidWhenLowQualityScore>DEACTIVE</ns1:raiseBidWhenLowQualityScore>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- TargetCpaBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyName>TARGET_CPA_BiddingStartegy</ns1:biddingStrategyName>
               <ns1:biddingScheme xsi:type="ns1:TargetCpaBiddingScheme">
                  <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                  <ns1:targetCpa>100</ns1:targetCpa>
                  <ns1:bidCeiling>50000</ns1:bidCeiling>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- TargetSpendBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyName>TARGET_SPEND_BiddingStartegy</ns1:biddingStrategyName>
               <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                  <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                  <ns1:bidCeiling>50000</ns1:bidCeiling>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- TargetRoasBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyName>TARGET_ROAS_BiddingStartegy</ns1:biddingStrategyName>
               <ns1:biddingScheme xsi:type="ns1:TargetRoasBiddingScheme">
                  <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                  <ns1:targetRoas>0.01</ns1:targetRoas>
                  <ns1:bidCeiling>50000</ns1:bidCeiling>
                  <ns1:bidFloor>5000</ns1:bidFloor>
               </ns1:biddingScheme>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
### Response
Reponse Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategyReturnValue.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>BiddingStrategyService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>BiddingStartegyReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000002</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>ENHANCED_CPC_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000003</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>PAGE_ONE_PROMOTED_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                     <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                     <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                     <ns1:bidCeiling>50000</ns1:bidCeiling>
                     <ns1:bidMultiplier>10.00</ns1:bidMultiplier>
                     <ns1:bidChangesForRaisesOnly>ACTIVE</ns1:bidChangesForRaisesOnly>
                     <ns1:raiseBidWhenBudgetConstrained>DEACTIVE</ns1:raiseBidWhenBudgetConstrained>
                     <ns1:raiseBidWhenLowQualityScore>DEACTIVE</ns1:raiseBidWhenLowQualityScore>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000004</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_CPA_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetCpaBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                     <ns1:targetCpa>100</ns1:targetCpa>
                     <ns1:bidCeiling>50000</ns1:bidCeiling>
                     <ns1:bidFloor>0</ns1:bidFloor>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000005</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_SPEND_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                     <ns1:bidCeiling>50000</ns1:bidCeiling>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000006</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_ROAS_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetRoasBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                     <ns1:targetRoas>0.01</ns1:targetRoas>
                     <ns1:bidCeiling>50000</ns1:bidCeiling>
                     <ns1:bidFloor>5000</ns1:bidFloor>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate (SET)
### Request
Updates an auto bidding.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [BiddingStrategyOperation](../data/BiddingStrategyOperation.md) | Updates auto bidding information | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>1111111111</ns1:accountId>
            <!-- EnhancedCpcBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>2222222222</ns1:biddingStrategyId>
               <ns1:biddingStrategyName>MODIFY_ENHANCED_CPC_BiddingStartegy</ns1:biddingStrategyName>
               <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                  <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- PageOnePromotedBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>3333333333</ns1:biddingStrategyId>
               <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                  <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                  <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                  <ns1:bidCeiling>10000</ns1:bidCeiling>
                  <ns1:bidMultiplier>50.00</ns1:bidMultiplier>
                  <ns1:bidChangesForRaisesOnly>DEACTIVE</ns1:bidChangesForRaisesOnly>
                  <ns1:raiseBidWhenBudgetConstrained>ACTIVE</ns1:raiseBidWhenBudgetConstrained>
                  <ns1:raiseBidWhenLowQualityScore>ACTIVE</ns1:raiseBidWhenLowQualityScore>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- TargetCpaBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>4444444444</ns1:biddingStrategyId>
               <ns1:biddingScheme xsi:type="ns1:TargetCpaBiddingScheme">
                  <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                  <ns1:targetCpa>250</ns1:targetCpa>
                  <ns1:bidCeiling>10000</ns1:bidCeiling>
                  <ns1:bidFloor>100</ns1:bidFloor>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- TargetSpendBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>5555555555</ns1:biddingStrategyId>
               <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                  <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                  <ns1:bidCeiling>3500</ns1:bidCeiling>
               </ns1:biddingScheme>
            </ns1:operand>
            <!-- TargetRoasBidding -->
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>6666666666</ns1:biddingStrategyId>
               <ns1:biddingScheme xsi:type="ns1:TargetRoasBiddingScheme">
                  <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                  <ns1:targetRoas>0.15</ns1:targetRoas>
                  <ns1:bidCeiling>1000</ns1:bidCeiling>
                  <!--設定済みのbidFloorを解除する。-->
                  <ns1:bidFloor>0</ns1:bidFloor>
               </ns1:biddingScheme>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategyReturnValue.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
 <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>BiddingStrategyService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>BiddingStartegyReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000002</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>MODIFY_ENHANCED_CPC_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000003</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>PAGE_ONE_PROMOTED_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                  <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                     <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                     <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                     <ns1:bidCeiling>10000</ns1:bidCeiling>
                     <ns1:bidMultiplier>50.00</ns1:bidMultiplier>
                     <ns1:bidChangesForRaisesOnly>DEACTIVE</ns1:bidChangesForRaisesOnly>
                     <ns1:raiseBidWhenBudgetConstrained>ACTIVE</ns1:raiseBidWhenBudgetConstrained>
                     <ns1:raiseBidWhenLowQualityScore>ACTIVE</ns1:raiseBidWhenLowQualityScore>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000004</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_CPA_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetCpaBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                     <ns1:targetCpa>250</ns1:targetCpa>
                     <ns1:bidCeiling>10000</ns1:bidCeiling>
                     <ns1:bidFloor>100</ns1:bidFloor>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000005</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_SPEND_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                     <ns1:bidCeiling>3500</ns1:bidCeiling>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000006</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_ROAS_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetRoasBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                     <ns1:targetRoas>0.15</ns1:targetRoas>
                     <ns1:bidCeiling>1000</ns1:bidCeiling>
                     <ns1:bidFloor>0</ns1:bidFloor>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate (REMOVE)
### Request
Delete the Auto bidding setting.

| Fieled | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [BiddingStrategyOperation](../data/BiddingStrategyOperation.md) | Deletes the Auto bidding information. | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>REMOVE</ns1:operator>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>2222222222</ns1:biddingStrategyId>
           </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>3333333333</ns1:biddingStrategyId>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>4444444444</ns1:biddingStrategyId>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>5555555555</ns1:biddingStrategyId>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1111111111</ns1:accountId>
               <ns1:biddingStrategyId>6666666666</ns1:biddingStrategyId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategyReturnValue.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>BiddingStrategyService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>BiddingStartegyReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000002</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>MODIFY_ENHANCED_CPC_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000003</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>PAGE_ONE_PROMOTED_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                     <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                     <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                     <ns1:bidCeiling>10000</ns1:bidCeiling>
                     <ns1:bidMultiplier>50.00</ns1:bidMultiplier>
                     <ns1:bidChangesForRaisesOnly>DEACTIVE</ns1:bidChangesForRaisesOnly>
                     <ns1:raiseBidWhenBudgetConstrained>ACTIVE</ns1:raiseBidWhenBudgetConstrained>
                     <ns1:raiseBidWhenLowQualityScore>ACTIVE</ns1:raiseBidWhenLowQualityScore>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000004</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_CPA_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetCpaBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                     <ns1:targetCpa>250</ns1:targetCpa>
                     <ns1:bidCeiling>10000</ns1:bidCeiling>
                     <ns1:bidFloor>100</ns1:bidFloor>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000005</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_SPEND_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                     <ns1:bidCeiling>3500</ns1:bidCeiling>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:biddingStrategy>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:biddingStrategyId>00000006</ns1:biddingStrategyId>
                  <ns1:biddingStrategyName>TARGET_ROAS_BiddingStartegy</ns1:biddingStrategyName>
                  <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                  <ns1:biddingScheme xsi:type="ns1:TargetRoasBiddingScheme">
                     <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                     <ns1:targetRoas>0.15</ns1:targetRoas>
                     <ns1:bidCeiling>1000</ns1:bidCeiling>
                     <ns1:bidFloor>0</ns1:bidFloor>
                  </ns1:biddingScheme>
               </ns1:biddingStrategy>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
