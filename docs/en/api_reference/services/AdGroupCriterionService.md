# AdGroupCriterionService
Use this service to get, add, update, or delete criteria (such as keyword). <br>
A criterion explains the conditions that determine if an ad should display.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.2/AdGroupCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.2/AdGroupCriterionService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Use this service to get, add, update, or delete adgroup criteria.
#### Operation
Explains the operation which provides at AdGroupCriterionService.
## get
### Request
Gets criteria of adgroup

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [AdGroupCriterionSelector](../data/AdGroupCriterionSelector.md) | Filters the adgroup criteria to be returned. |

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>xxxxxxxx</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <ns1:campaignIds>xxxxxxxx</ns1:campaignIds>
                <ns1:campaignIds>xxxxxxxx</ns1:campaignIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                <ns1:userStatuses>ACTIVE</ns1:userStatuses>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>PRE_DISAPPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>POST_DISAPPROVED</ns1:approvalStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
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
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>xxxxxxxx</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <ns1:campaignIds>xxxxxxxx</ns1:campaignIds>
                <ns1:campaignIds>xxxxxxxx</ns1:campaignIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                <ns1:userStatuses>ACTIVE</ns1:userStatuses>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>PRE_DISAPPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>POST_DISAPPROVED</ns1:approvalStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate (ADD)
### Request
Adds adgroup criteria.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterionOperation.md) | Operations to do during checks on keywords to be added. | 

##### Request Sample [Biddable settings]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>xxxxxxxx</ns1:apiAccountPassword>
            <ns1:accountId>xxxxxxxx</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>xxxxxxxx</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                <ns1:operand xsi:type="ns1:NegativeAdGroupCriterion">
                    <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:text>keyword</ns1:text>
                        <ns1:matchType>EXACT</ns1:matchType>
                    </ns1:criterion>
                </ns1:operand>
                <ns1:operand xsi:type="ns1:NegativeAdGroupCriterion">
                    <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:text>term</ns1:text>
                        <ns1:matchType>EXACT</ns1:matchType>
                    </ns1:criterion>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [Negative settings]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>xxxxxxxx</ns1:apiAccountPassword>
            <ns1:accountId>xxxxxxxx</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>xxxxxxxx</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                <ns1:operand xsi:type="ns1:NegativeAdGroupCriterion">
                    <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:text>keyword</ns1:text>
                        <ns1:matchType>EXACT</ns1:matchType>
                    </ns1:criterion>
                </ns1:operand>
                <ns1:operand xsi:type="ns1:NegativeAdGroupCriterion">
                    <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:text>term</ns1:text>
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
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterionReturnValue.md) | Added and updated adgroup criteria. | 

##### Response Sample [Biddable settings]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
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
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaignName</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                  <ns1:adGroupName>adGroupName</ns1:adGroupName>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>xxxxxxxx</ns1:criterionId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>testtesttest1</ns1:text>
                     <ns1:matchType>EXACT</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>sumstatus</ns1:disapprovalReasonCodes>
                  <ns1:destinationUrl>http://wwww.yahoo.co.jp</ns1:destinationUrl>
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
               </ns1:adGroupCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample [Negative settings]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
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
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupCriterion xsi:type="ns1:NegativeAdGroupCriterion">
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:campaignName>campaignName</ns1:campaignName>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:adGroupName>adGroupName</ns1:adGroupName>
                        <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                        <ns1:criterion xsi:type="ns1:Keyword">
                            <ns1:criterionId>xxxxxxxx</ns1:criterionId>
                            <ns1:type>KEYWORD</ns1:type>
                            <ns1:text>keyword</ns1:text>
                            <ns1:matchType>EXACT</ns1:matchType>
                        </ns1:criterion>
                    </ns1:adGroupCriterion>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupCriterion xsi:type="ns1:NegativeAdGroupCriterion">
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:campaignName>campaignName</ns1:campaignName>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:adGroupName>adGroupName</ns1:adGroupName>
                        <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                        <ns1:criterion xsi:type="ns1:Keyword">
                            <ns1:criterionId>xxxxxxxx</ns1:criterionId>
                            <ns1:type>KEYWORD</ns1:type>
                            <ns1:text>term</ns1:text>
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
### Request
| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterionOperation.md) | Operations to do during checks on keywords to be added. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>xxxxxxxx</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>xxxxxxxx</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>xxxxxxxx</ns1:accountId>
            <ns1:campaignId>xxxxxxxx</ns1:campaignId>
            <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
            <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
            <ns1:operand xsi:type="ns1:BiddableAdGroupCriterion">
               <ns1:accountId>xxxxxxxx</ns1:accountId>
               <ns1:campaignId>xxxxxxxx</ns1:campaignId>
               <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
               <ns1:criterion xsi:type="ns1:Keyword">
                  <ns1:criterionId>xxxxxxxx</ns1:criterionId>
                  <ns1:type>KEYWORD</ns1:type>
                  <ns1:text>keyword1</ns1:text>
                  <ns1:matchType>EXACT</ns1:matchType>
               </ns1:criterion>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:destinationUrl>http://www.yahoo.co.jp</ns1:destinationUrl>
               <ns1:biddingStrategyConfiguration>
                  <!--設定した入札価格を取消す-->
                  <ns1:bid>
                     <ns1:maxCpc>0</ns1:maxCpc>
                  </ns1:bid>
               </ns1:biddingStrategyConfiguration>
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
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterionReturnValue.md) | Added and updated adgroup criteria (without optional parts). | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
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
            <ns1:values>
               <ns1:operationSucceeded>1</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
               <ns1:accountId>xxxxxxxx</ns1:accountId>
               <ns1:campaignId>xxxxxxxx</ns1:campaignId>
               <ns1:campaignName>campaign name</ns1:campaignName>
               <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
               <ns1:adGroupName>ad group name</ns1:adGroupName>
               <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
               <ns1:criterion xsi:type="ns1:Keyword">
                  <ns1:criterionId>xxxxxxxx</ns1:criterionId>
                  <ns1:type>KEYWORD</ns1:type>
                  <ns1:text>keyword1</ns1:text>
                  <ns1:matchType>EXACT</ns1:matchType>
               </ns1:criterion>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>sumstatus</ns1:disapprovalReasonCodes>
                  <ns1:destinationUrl>http://wwww.yahoo.co.jp</ns1:destinationUrl>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                     <ns1:bid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                        <ns1:bidSource>ADGROUP</ns1:bidSource>
                        <ns1:adGroupMaxCpc>120</ns1:adGroupMaxCpc>
                     </ns1:bid>
                     <ns1:parentBiddingStrategyConfigurations>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                        <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                           <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                        </ns1:biddingScheme>
                     </ns1:parentBiddingStrategyConfigurations>
                  </ns1:biddingStrategyConfiguration>
               </ns1:adGroupCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
### Request
Removes adgroup criteria.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AdGroupCriterionOperation](../data/AdGroupCriterionOperation.md) | Operations to do during checks on keywords to be added. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>xxxxxxxx</ns1:apiAccountPassword>
            <ns1:accountId>xxxxxxxx</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>xxxxxxxx</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                <ns1:operand xsi:type="ns1:BiddableAdGroupCriterion">
                    <ns1:accountId>xxxxxxxx</ns1:accountId>
                    <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                    <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:criterionId>xxxxxxxx</ns1:criterionId>
                    </ns1:criterion>
                </ns1:operand>
                <ns1:operand xsi:type="ns1:BiddableAdGroupCriterion">
                    <ns1:accountId>xxxxxxxx</ns1:accountId>
                    <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                    <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:criterionId>xxxxxxxx</ns1:criterionId>
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
| rval | [AdGroupCriterionReturnValue](../data/AdGroupCriterionReturnValue.md) | Added and updated adgroup criteria (without optional parts). |

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
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
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupCriterion xsi:type="ns1:BiddableAdGroupCriterion">
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                  <ns1:criterionUse>BIDDABLE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>xxxxxxxx</ns1:criterionId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>keyword1</ns1:text>
                     <ns1:matchType>EXACT</ns1:matchType>
                  </ns1:criterion>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                  <ns1:disapprovalReasonCodes>sumstatus</ns1:disapprovalReasonCodes>
                  <ns1:destinationUrl>http://wwww.yahoo.co.jp</ns1:destinationUrl>
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
               </ns1:adGroupCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
