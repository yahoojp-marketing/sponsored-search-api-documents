# AdGroupCriterionService
Use this service to get, add, update, or delete Ad group criteria (such as keyword). <br>
A criterion explains the conditions that determine if an ad should display.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V6.0/AdGroupCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V6.0/AdGroupCriterionService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Use this service to get, add, update, or delete Ad group criteria.

#### Operation
Explains the operation which provides at AdGroupCriterionService.

## get
### Request
Gets criteria of Ad group.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [AdGroupCriterionSelector](../data/AdGroupCriterionSelector.md) | Filters the adgroup criteria to be returned. |

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6">
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
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Field

| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupCriterionPage](../data/AdGroupCriterionPage.md) | A page (subset) view of the criteria selected. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
   xmlns:ns1="http://ss.yahooapis.jp/V6"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupCriterionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>3</ns1:totalNumEntries>
            <ns1:Page.Type>AdGroupCriterionPage</ns1:Page.Type>
            <!-- Keyword before the Advanced URL upgrade -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000001</ns1:criterionId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>testtesttest1</ns1:text>
                     <ns1:matchType>EXACT</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>sumstatus</ns1:disapprovalReasonCodes>
                  <ns1:destinationUrl>http://wwww.yahoo.co.jp</ns1:destinationUrl>
                  <ns1:reviewDestinationUrl>http://wwww.test.co.jp</ns1:reviewDestinationUrl>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:bid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>CRITERION</ns1:bidSource>
                        <ns1:adGroupMaxCpc>120</ns1:adGroupMaxCpc>
                        <ns1:keywordMaxCpc>120</ns1:keywordMaxCpc>
                     </ns1:bid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:advanced>FALSE</ns1:advanced>
               </ns1:adGroupCriterion>
            </ns1:values>
            <!-- Keyword after the Advanced URL upgrade -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000002</ns1:criterionId>
                     <ns1:criterionTrackId>333333</ns1:criterionTrackId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>キーワード</ns1:text>
                     <ns1:matchType>PHRASE</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>1000000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>自動入札名1</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:bid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>CRITERION</ns1:bidSource>
                        <ns1:adGroupMaxCpc>120</ns1:adGroupMaxCpc>
                        <ns1:keywordMaxCpc>120</ns1:keywordMaxCpc>
                     </ns1:bid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyId>1000000002</ns1:biddingStrategyId>
                        <ns1:biddingStrategyName>自動入札名2</ns1:biddingStrategyName>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:reviewAdvancedUrl>http://www.yahoo.co.jp</ns1:reviewAdvancedUrl>
                  <ns1:reviewTrackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:reviewTrackingUrl>
                  <ns1:reviewCustomParameters>
                    <ns1:isRemove>FALSE</ns1:isRemove>
                    <ns1:parameters>
                      <ns1:key>site</ns1:key>
                      <ns1:value>yahoo</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id1</ns1:key>
                      <ns1:value>1234</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id2</ns1:key>
                      <ns1:value>a7h59A98yu</ns1:value>
                    </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:adGroupCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
### Request
Create Ad group criteria.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterionOperation.md) | Operations to do during checks on keywords to be added. | 

##### Request Sample [Biddable settings]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
<!-- BiddableAdGroupCriterion -->
            <ns1:operand xsi:type="ns1:BiddableAdGroupCriterion">
               <ns1:campaignId>1000000001</ns1:campaignId>
               <ns1:adGroupId>1000000001</ns1:adGroupId>
               <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
               <ns1:criterion xsi:type="ns1:Keyword">
                  <ns1:type>KEYWORD</ns1:type>
                  <ns1:text>キーワード</ns1:text>
                  <ns1:matchType>PHRASE</ns1:matchType>
               </ns1:criterion>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:biddingStrategyConfiguration>
                  <ns1:bid>
                     <ns1:maxCpc>120</ns1:maxCpc>
                  </ns1:bid>
               </ns1:biddingStrategyConfiguration>
               <ns1:advancedUrl>http://www.yahoo.co.jp</ns1:advancedUrl>
               <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
               <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
               <ns1:customParameters>
                 <ns1:isRemove>FALSE</ns1:isRemove>
                 <ns1:parameters>
                   <ns1:key>site</ns1:key>
                   <ns1:value>yahoo</ns1:value>
                 </ns1:parameters>
                 <ns1:parameters>
                   <ns1:key>id1</ns1:key>
                   <ns1:value>1234</ns1:value>
                 </ns1:parameters>
                 <ns1:parameters>
                   <ns1:key>id2</ns1:key>
                   <ns1:value>a7h59A98yu</ns1:value>
                 </ns1:parameters>
               </ns1:customParameters>
               <ns1:advanced>TRUE</ns1:advanced>
            </ns1:operand>
<!-- NegativeAdGroupCriterion -->
            <ns1:operand xsi:type="ns1:NegativeAdGroupCriterion">
               <ns1:campaignId>1000000001</ns1:campaignId>
               <ns1:adGroupId>1000000001</ns1:adGroupId>
               <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
               <ns1:criterion xsi:type="ns1:Keyword">
                   <ns1:type>KEYWORD</ns1:type>
                   <ns1:text>対象外キーワード</ns1:text>
                   <ns1:matchType>EXACT</ns1:matchType>
               </ns1:criterion>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterionReturnValue.md) | Ad group criteria. | 

##### Response Sample [Biddable settings]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupCriterionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AdGroupCriterionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
<!-- BiddableAdGroupCriterion -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000001</ns1:criterionId>
                     <ns1:criterionTrackId>333333</ns1:criterionTrackId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>キーワード</ns1:text>
                     <ns1:matchType>PHRASE</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>1000000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>自動入札名1</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:bid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>CRITERION</ns1:bidSource>
                        <ns1:adGroupMaxCpc>120</ns1:adGroupMaxCpc>
                        <ns1:keywordMaxCpc>120</ns1:keywordMaxCpc>
                     </ns1:bid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyId>1000000002</ns1:biddingStrategyId>
                        <ns1:biddingStrategyName>自動入札名2</ns1:biddingStrategyName>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:reviewAdvancedUrl>http://www.yahoo.co.jp</ns1:reviewAdvancedUrl>
                  <ns1:reviewAdvancedMobileUrl>http://aaaa.jp/mb</ns1:reviewAdvancedMobileUrl>
                  <ns1:reviewTrackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:reviewTrackingUrl>
                  <ns1:reviewCustomParameters>
                    <ns1:isRemove>FALSE</ns1:isRemove>
                    <ns1:parameters>
                      <ns1:key>site</ns1:key>
                      <ns1:value>yahoo</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id1</ns1:key>
                      <ns1:value>1234</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id2</ns1:key>
                      <ns1:value>a7h59A98yu</ns1:value>
                    </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:adGroupCriterion>
            </ns1:values>
<!-- NegativeAdGroupCriterion -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:NegativeAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000002</ns1:criterionId>
                     <ns1:criterionTrackId>444444</ns1:criterionTrackId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>対象外キーワード</ns1:text>
                     <ns1:matchType>EXACT</ns1:matchType>
                  </ns1:criterion>
               </ns1:adGroupCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Upgrade or change Ad group criteria.

### Request
| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterionOperation.md) | Operations to do during checks on keywords to be added. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
   xmlns:ns1="http://ss.yahooapis.jp/V6"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
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
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand xsi:type="ns1:BiddableAdGroupCriterion">
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000001</ns1:adGroupId>
               <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
               <ns1:criterion xsi:type="ns1:Keyword">
                  <ns1:criterionId>1000000001</ns1:criterionId>
                  <ns1:type>KEYWORD</ns1:type>
               </ns1:criterion>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:biddingStrategyConfiguration>
                  <ns1:bid>
                     <ns1:maxCpc>0</ns1:maxCpc>
                  </ns1:bid>
               </ns1:biddingStrategyConfiguration>
               <ns1:advancedUrl>http://test.jp</ns1:advancedUrl>
               <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
               <ns1:customParameters>
                 <ns1:isRemove>FALSE</ns1:isRemove>
                 <ns1:parameters>
                   <ns1:key>site</ns1:key>
                   <ns1:value>aaaa</ns1:value>
                 </ns1:parameters>
                 <ns1:parameters>
                   <ns1:key>id1</ns1:key>
                   <ns1:value>9999</ns1:value>
                 </ns1:parameters>
                 <ns1:parameters>
                   <ns1:key>id2</ns1:key>
                   <ns1:value>a7h59A98yu</ns1:value>
                 </ns1:parameters>
               </ns1:customParameters>
               <ns1:advanced>TRUE</ns1:advanced>
            </ns1:operand>
<!-- Delete of Custom parameter -->
            <ns1:operand xsi:type="ns1:BiddableAdGroupCriterion">
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000001</ns1:adGroupId>
               <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
               <ns1:criterion xsi:type="ns1:Keyword">
                  <ns1:criterionId>1000000002</ns1:criterionId>
                  <ns1:type>KEYWORD</ns1:type>
               </ns1:criterion>
               <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}</ns1:trackingUrl>
               <ns1:customParameters>
                 <ns1:isRemove>TRUE</ns1:isRemove>
               </ns1:customParameters>
               <ns1:advanced>TRUE</ns1:advanced>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Field

| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterionReturnValue.md) | Ad group criteria (without optional parts). | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
   xmlns:ns1="http://ss.yahooapis.jp/V6"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupCriterionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AdGroupCriterionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
<!-- BiddableAdGroupCriterion -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000001</ns1:criterionId>
                     <ns1:criterionTrackId>333333</ns1:criterionTrackId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>キーワード</ns1:text>
                     <ns1:matchType>PHRASE</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>1000000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>自動入札名1</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:bid>
                        <ns1:maxCpc>0</ns1:maxCpc>
                        <ns1:bidSource>CRITERION</ns1:bidSource>
                        <ns1:adGroupMaxCpc>120</ns1:adGroupMaxCpc>
                        <ns1:keywordMaxCpc>120</ns1:keywordMaxCpc>
                     </ns1:bid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyId>1000000002</ns1:biddingStrategyId>
                        <ns1:biddingStrategyName>自動入札名2</ns1:biddingStrategyName>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:advancedUrl>http://www.yahoo.co.jp</ns1:advancedUrl>
                  <ns1:reviewAdvancedUrl>http://test.jp</ns1:reviewAdvancedUrl>
                  <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                  <ns1:reviewTrackingUrl>http://test.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:reviewTrackingUrl>
                  <ns1:customParameters>
                    <ns1:isRemove>FALSE</ns1:isRemove>
                    <ns1:parameters>
                      <ns1:key>site</ns1:key>
                      <ns1:value>yahoo</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id1</ns1:key>
                      <ns1:value>1234</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id2</ns1:key>
                      <ns1:value>a7h59A98yu</ns1:value>
                    </ns1:parameters>
                  </ns1:customParameters>
                  <ns1:reviewCustomParameters>
                    <ns1:isRemove>FALSE</ns1:isRemove>
                    <ns1:parameters>
                      <ns1:key>site</ns1:key>
                      <ns1:value>aaaa</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id1</ns1:key>
                      <ns1:value>9999</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id2</ns1:key>
                      <ns1:value>a7h59A98yu</ns1:value>
                    </ns1:parameters>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:adGroupCriterion>
            </ns1:values>
<!-- BiddableAdGroupCriterion (Delete of Custom parameter) -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000002</ns1:criterionId>
                     <ns1:criterionTrackId>444444</ns1:criterionTrackId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>キーワード2</ns1:text>
                     <ns1:matchType>PHRASE</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>1000000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>自動入札名1</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:bid>
                        <ns1:maxCpc>0</ns1:maxCpc>
                        <ns1:bidSource>CRITERION</ns1:bidSource>
                        <ns1:adGroupMaxCpc>120</ns1:adGroupMaxCpc>
                        <ns1:keywordMaxCpc>120</ns1:keywordMaxCpc>
                     </ns1:bid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyId>1000000002</ns1:biddingStrategyId>
                        <ns1:biddingStrategyName>自動入札名2</ns1:biddingStrategyName>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:advancedUrl>http://www.yahoo.co.jp</ns1:advancedUrl>
                  <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                  <ns1:reviewTrackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}</ns1:reviewTrackingUrl>
                  <ns1:customParameters>
                    <ns1:isRemove>FALSE</ns1:isRemove>
                    <ns1:parameters>
                      <ns1:key>site</ns1:key>
                      <ns1:value>yahoo</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id1</ns1:key>
                      <ns1:value>1234</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id2</ns1:key>
                      <ns1:value>a7h59A98yu</ns1:value>
                    </ns1:parameters>
                  </ns1:customParameters>
                  <ns1:reviewCustomParameters>
                    <ns1:isRemove>TRUE</ns1:isRemove>
                  </ns1:reviewCustomParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:adGroupCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
### Request
Removes Ad group criteria.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterionOperation.md) | Operations to do during checks on keywords to be added. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
<!-- BiddableAdGroupCriterion -->
                <ns1:operand xsi:type="ns1:BiddableAdGroupCriterion">
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000001</ns1:adGroupId>
                    <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:criterionId>100000001</ns1:criterionId>
                        <ns1:type>KEYWORD</ns1:type>
                    </ns1:criterion>
                </ns1:operand>
<!-- NegativeAdGroupCriterion -->
                <ns1:operand xsi:type="ns1:NegativeAdGroupCriterion">
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000001</ns1:adGroupId>
                    <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:criterionId>100000002</ns1:criterionId>
                        <ns1:type>KEYWORD</ns1:type>
                    </ns1:criterion>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Field

| Field | Data Type | Description | 
|---|---|---|
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterionReturnValue.md) | Ad group criteria (without optional parts). |

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
   xmlns:ns1="http://ss.yahooapis.jp/V6"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupCriterionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AdGroupCriterionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
<!-- BiddableAdGroupCriterion -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000001</ns1:criterionId>
                     <ns1:criterionTrackId>333333</ns1:criterionTrackId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>キーワード</ns1:text>
                     <ns1:matchType>PHRASE</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>1000000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>自動入札名1</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:bid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>CRITERION</ns1:bidSource>
                        <ns1:adGroupMaxCpc>120</ns1:adGroupMaxCpc>
                        <ns1:keywordMaxCpc>120</ns1:keywordMaxCpc>
                     </ns1:bid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyId>1000000002</ns1:biddingStrategyId>
                        <ns1:biddingStrategyName>自動入札名2</ns1:biddingStrategyName>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:advancedUrl>http://www.yahoo.co.jp</ns1:advancedUrl>
                  <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
                  <ns1:customParameters>
                    <ns1:isRemove>FALSE</ns1:isRemove>
                    <ns1:parameters>
                      <ns1:key>site</ns1:key>
                      <ns1:value>yahoo</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id1</ns1:key>
                      <ns1:value>1234</ns1:value>
                    </ns1:parameters>
                    <ns1:parameters>
                      <ns1:key>id2</ns1:key>
                      <ns1:value>a7h59A98yu</ns1:value>
                    </ns1:parameters>
                  </ns1:customParameters>
                  <ns1:advanced>TRUE</ns1:advanced>
               </ns1:adGroupCriterion>
            </ns1:values>
<!-- NegativeAdGroupCriterion -->
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:NegativeAdGroupCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>1000000001</ns1:adGroupId>
                  <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                  <ns1:adGroupName>ad group name</ns1:adGroupName>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>1000000002</ns1:criterionId>
                     <ns1:criterionTrackId>444444</ns1:criterionTrackId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>対象外キーワード</ns1:text>
                     <ns1:matchType>EXACT</ns1:matchType>
                  </ns1:criterion>
               </ns1:adGroupCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
