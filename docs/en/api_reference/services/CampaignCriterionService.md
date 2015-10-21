# CampaignCriterionService
CampaignCriterionService is to get, add, or delete negative criteria in campaign-level.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/CampaignCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/CampaignCriterionService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Get, add, or delete negative criteria in campaign-level.
#### Operation
Explains the operation which provides at CampaignCriterionService.
## get
### Request
Gets negative criteria in campaign-level.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [CampaignCriterionSelector](../data/CampaignCriterionSelector.md) | Filters the campaign criteria to apply. | 

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
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:campaignIds>100000001</ns1:campaignIds>
                <ns1:campaignIds>100000002</ns1:campaignIds>
                <ns1:criterionIds>100000005</ns1:criterionIds>
                <ns1:criterionIds>100000006</ns1:criterionIds>
                <ns1:criterionIds>100000007</ns1:criterionIds>
                <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignCriterionPage](../data/CampaignCriterionPage.md) | Campaign criteria | 

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignCriterionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:Page.Type>CampaignCriterionPage</ns1:Page.Type>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignCriterion xsi:type="ns1:NegativeCampaignCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>101010101</ns1:criterionId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>keyword keyword2</ns1:text>
                     <ns1:matchType>EXACT</ns1:matchType>
                  </ns1:criterion>
               </ns1:campaignCriterion>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignCriterion xsi:type="ns1:NegativeCampaignCriterion">
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:campaignId>100000001</ns1:campaignId>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>yahoo bigkeyword2</ns1:text>
                     <ns1:matchType>BROAD</ns1:matchType>
                  </ns1:criterion>
               </ns1:campaignCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate (ADD)
### Request
Add negative criteria in campaign-level.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operation | Req | [CampaignCriterionOperation](../data/CampaignCriterionOperation.md) | Campaign criteria and the job process of target. | 

##### Request Sample
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
                <ns1:campaignId>100000001</ns1:campaignId>
                <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                <ns1:operand xsi:type="ns1:NegativeCampaignCriterion">
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:text>yahoo bigkeyword1</ns1:text>
                        <ns1:matchType>BROAD</ns1:matchType>
                    </ns1:criterion>
                </ns1:operand>
                <ns1:operand xsi:type="ns1:NegativeCampaignCriterion">
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:text>yahoo bigkeyword2</ns1:text>
                        <ns1:matchType>BROAD</ns1:matchType>
                    </ns1:criterion>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Reponse Field

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignCriterionReturnValue](../data/CampaignCriterionReturnValue.md) | Container for campaign criteria including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignCriterionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignCriterionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignCriterion xsi:type="ns1:NegativeCampaignCriterion">
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:campaignId>100000001</ns1:campaignId>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>yahoo bigkeyword1</ns1:text>
                     <ns1:matchType>BROAD</ns1:matchType>
                  </ns1:criterion>
               </ns1:campaignCriterion>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignCriterion xsi:type="ns1:NegativeCampaignCriterion">
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:campaignId>100000001</ns1:campaignId>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>yahoo bigkeyword2</ns1:text>
                     <ns1:matchType>BROAD</ns1:matchType>
                  </ns1:criterion>
               </ns1:campaignCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate (REMOVE)
### Request
Removed negative criteria in campaign-level.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operation | Req | [CampaignCriterionOperation](../data/CampaignCriterionOperation.md) | Campaign criteria and the job process of target. | 

##### Request Sample
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
                <ns1:campaignId>100000001</ns1:campaignId>
                <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                <ns1:operand xsi:type="ns1:NegativeCampaignCriterion">
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:criterionId>100000001</ns1:criterionId>
                    </ns1:criterion>
                </ns1:operand>
                <ns1:operand xsi:type="ns1:NegativeCampaignCriterion">
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                    <ns1:criterion xsi:type="ns1:Keyword">
                        <ns1:type>KEYWORD</ns1:type>
                        <ns1:criterionId>100000001</ns1:criterionId>
                    </ns1:criterion>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignCriterionReturnValue](../data/CampaignCriterionReturnValue.md) | Container for campaign criteria including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignCriterionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignCriterionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignCriterion xsi:type="ns1:NegativeCampaignCriterion">
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>1000000001</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:criterionId>101010101</ns1:criterionId>
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:text>keyword keyword2</ns1:text>
                     <ns1:matchType>EXACT</ns1:matchType>
                  </ns1:criterion>
               </ns1:campaignCriterion>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignCriterion xsi:type="ns1:NegativeCampaignCriterion">
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:campaignId>100000002</ns1:campaignId>
                  <ns1:criterionUse>NEGATIVE</ns1:criterionUse>
                  <ns1:criterion xsi:type="ns1:Keyword">
                     <ns1:type>KEYWORD</ns1:type>
                     <ns1:criterionId>100000001</ns1:criterionId>
                  </ns1:criterion>
               </ns1:campaignCriterion>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
