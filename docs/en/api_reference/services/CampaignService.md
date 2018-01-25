# CampaignService
CampaignService is to get, add, update, or remove campaigns.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/CampaignService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/CampaignService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Service Overview
Get, add, update, or remove campaigns.

#### Operation
Explains the operation which provides at CampaignService.

## get
Gets information related to campaigns.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [CampaignSelector](../data/CampaignSelector.md) | The campaign selector for operations. | 

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
        <ns1:campaignIds>100000001</ns1:campaignIds>
        <ns1:campaignIds>100000002</ns1:campaignIds>
        <ns1:campaignIds>100000003</ns1:campaignIds>
        <ns1:campaignIds>200000001</ns1:campaignIds>
        <ns1:campaignIds>200000002</ns1:campaignIds>
        <ns1:campaignIds>200000003</ns1:campaignIds>
        <ns1:campaignIds>200000004</ns1:campaignIds>
        <ns1:campaignIds>200000005</ns1:campaignIds>
        <ns1:userStatuses>ACTIVE</ns1:userStatuses>
        <ns1:userStatuses>PAUSED</ns1:userStatuses>
        <ns1:biddingStrategyIds>10000000001</ns1:biddingStrategyIds>
        <ns1:biddingStrategyIds>10000000002</ns1:biddingStrategyIds>
        <ns1:biddingStrategyIds>10000000003</ns1:biddingStrategyIds>
        <ns1:biddingStrategyIds>10000000004</ns1:biddingStrategyIds>
        <ns1:biddingStrategyIds>10000000005</ns1:biddingStrategyIds>
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
Response Fields in normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignPage](../data/CampaignPage.md) | Entry of acquired campaign. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>CampaignService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>CampaignPage</ns1:Page.Type>
       <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000004</ns1:campaignId>
            <ns1:campaignTrackId>3000000004</ns1:campaignTrackId>
            <ns1:campaignName>campaign name</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20101201</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:settings xsi:type="ns1:TargetingSetting">
             <ns1:type>TARGET_LIST_SETTING</ns1:type>
              <ns1:targetAll>ACTIVE</ns1:targetAll>
            </ns1:settings>                       
            <ns1:campaignType>STANDARD</ns1:campaignType>
            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
            <ns1:customParameters>
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
            <ns1:urlReviewData>
              <ns1:urlApprovalStatus>APPROVED</ns1:urlApprovalStatus>
            </ns1:urlReviewData>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000005</ns1:campaignId>
            <ns1:campaignTrackId>3000000005</ns1:campaignTrackId>
            <ns1:campaignName>campaign name</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20101201</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:settings xsi:type="ns1:TargetingSetting">
             <ns1:type>TARGET_LIST_SETTING</ns1:type>
              <ns1:targetAll>DEACTIVE</ns1:targetAll>
            </ns1:settings>           
            <ns1:campaignType>MOBILE_APP</ns1:campaignType>
            <ns1:appStore>IOS</ns1:appStore>
            <ns1:appId>100000000000000</ns1:appId>
            <ns1:urlReviewData>
              <ns1:inReviewUrl>
                <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
              </ns1:inReviewUrl>
              <ns1:urlApprovalStatus>REVIEW</ns1:urlApprovalStatus>
            </ns1:urlReviewData>
          </ns1:campaign>
        </ns1:values>
     </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Add campaign information.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/CampaignOperation.md) | The Campaign selector for operations and list of operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>1234567890</ns1:accountId>
       <ns1:operand>
          <ns1:campaignName>STANDARD_MANUAL_CPC</ns1:campaignName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:startDate>20181101</ns1:startDate>
          <ns1:endDate>20371231</ns1:endDate>
          <ns1:budget>
            <ns1:period>DAILY</ns1:period>
            <ns1:amount>10000</ns1:amount>
            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
          </ns1:budget>
          <ns1:biddingStrategyConfiguration>
            <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
          </ns1:biddingStrategyConfiguration>
          <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
          <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
            <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
            <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
            <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
          </ns1:settings>
         <ns1:campaignType>STANDARD</ns1:campaignType>
          <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns1:trackingUrl>
          <ns1:customParameters>
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
        </ns1:operand>
       <ns1:operand>
          <ns1:campaignName>IOS_MANUAL_CPC</ns1:campaignName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:startDate>20181101</ns1:startDate>
          <ns1:endDate>20371231</ns1:endDate>
          <ns1:budget>
            <ns1:period>DAILY</ns1:period>
            <ns1:amount>10000</ns1:amount>
            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
          </ns1:budget>
          <ns1:biddingStrategyConfiguration>
            <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
          </ns1:biddingStrategyConfiguration>
          <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
          <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
            <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
            <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
            <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
          </ns1:settings>
          <ns1:settings xsi:type="ns1:TargetingSetting">
            <ns1:type>TARGET_LIST_SETTING</ns1:type>
            <ns1:targetAll>ACTIVE</ns1:targetAll>
          </ns1:settings>
          <ns1:campaignType>MOBILE_APP</ns1:campaignType>
          <ns1:appStore>IOS</ns1:appStore>
          <ns1:appId>sampleAppId</ns1:appId>
          <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns1:trackingUrl>
          <ns1:customParameters>
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
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields in normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | This object is a container for campaign information including operation results. |

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.2845</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>1234567890</ns1:accountId>
                  <ns1:campaignId>100001</ns1:campaignId>
                  <ns1:campaignTrackId>0</ns1:campaignTrackId>
                  <ns1:campaignName>STANDARD_MANUAL_CPCass</ns1:campaignName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:servingStatus>PENDING</ns1:servingStatus>
                  <ns1:startDate>20181101</ns1:startDate>
                  <ns1:endDate>20371231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:conversionOptimizerEligibility>DISABLE</ns1:conversionOptimizerEligibility>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                  </ns1:settings>
                  <ns1:settings xsi:type="ns1:TargetingSetting">
                     <ns1:type>TARGET_LIST_SETTING</ns1:type>
                     <ns1:targetAll>DEACTIVE</ns1:targetAll>
                  </ns1:settings>
                  <ns1:campaignType>STANDARD</ns1:campaignType>
                  <ns1:urlReviewData>
                     <ns1:inReviewUrl>
                        <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={_site}&pid={_id1}&vid={_id2}]]></ns1:trackingUrl>
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
                     </ns1:inReviewUrl>
                     <ns1:urlApprovalStatus>REVIEW</ns1:urlApprovalStatus>
                  </ns1:urlReviewData>
               </ns1:campaign>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>1234567890</ns1:accountId>
                  <ns1:campaignId>100002</ns1:campaignId>
                  <ns1:campaignTrackId>0</ns1:campaignTrackId>
                  <ns1:campaignName>IOS_MANUAL_CPCss</ns1:campaignName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:servingStatus>PENDING</ns1:servingStatus>
                  <ns1:startDate>20181101</ns1:startDate>
                  <ns1:endDate>20371231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:conversionOptimizerEligibility>DISABLE</ns1:conversionOptimizerEligibility>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                  </ns1:settings>
                  <ns1:settings xsi:type="ns1:TargetingSetting">
                     <ns1:type>TARGET_LIST_SETTING</ns1:type>
                     <ns1:targetAll>ACTIVE</ns1:targetAll>
                  </ns1:settings>
                  <ns1:campaignType>MOBILE_APP</ns1:campaignType>
                  <ns1:appStore>IOS</ns1:appStore>
                  <ns1:appId>sampleAppId</ns1:appId>
                  <ns1:urlReviewData>
                     <ns1:inReviewUrl>
                        <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={_site}&pid={_id1}&vid={_id2}]]></ns1:trackingUrl>
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
                     </ns1:inReviewUrl>
                     <ns1:urlApprovalStatus>REVIEW</ns1:urlApprovalStatus>
                  </ns1:urlReviewData>
               </ns1:campaign>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Updates the information related to campaigns.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/CampaignOperation.md) | The Campaign selector for operations and list of operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:operand>
               <ns1:campaignId>10001</ns1:campaignId>
               <ns1:settings xsi:type="ns1:TargetingSetting">
                  <ns1:type>TARGET_LIST_SETTING</ns1:type>
                  <ns1:targetAll>ACTIVE</ns1:targetAll>
               </ns1:settings>
            </ns1:operand>
            <ns1:operand>
               <ns1:campaignId>10002</ns1:campaignId>
               <ns1:settings xsi:type="ns1:TargetingSetting">
                  <ns1:type>TARGET_LIST_SETTING</ns1:type>
                  <ns1:targetAll>DEACTIVE</ns1:targetAll>
               </ns1:settings>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields in normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | This object is a container for campaign including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>10001</ns1:campaignId>
                  <ns1:campaignName>STANDARD_MANUAL_CPC</ns1:campaignName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:startDate>20170701</ns1:startDate>
                  <ns1:endDate>20371231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:adServingOptimizationStatus>CONVERSION_OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                  </ns1:settings>
                  <ns1:settings xsi:type="ns1:TargetingSetting">
                     <ns1:type>TARGET_LIST_SETTING</ns1:type>
                     <ns1:targetAll>ACTIVE</ns1:targetAll>
                  </ns1:settings>
                  <ns1:campaignType>STANDARD</ns1:campaignType>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
                  <ns1:customParameters>
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
               </ns1:campaign>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:campaignId>10002</ns1:campaignId>
                  <ns1:campaignName>IOS_MANUAL_CPC</ns1:campaignName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:startDate>20170701</ns1:startDate>
                  <ns1:endDate>20371231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                  </ns1:settings>
                  <ns1:settings xsi:type="ns1:TargetingSetting">
                     <ns1:type>TARGET_LIST_SETTING</ns1:type>
                     <ns1:targetAll>DEACTIVE</ns1:targetAll>
                  </ns1:settings>
                  <ns1:campaignType>MOBILE_APP</ns1:campaignType>
                  <ns1:appStore>IOS</ns1:appStore>
                  <ns1:appId>sampleAppId</ns1:appId>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
                  <ns1:customParameters>
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
               </ns1:campaign>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
Removes the inforamtion related to campaigns.

### Request
| Parameter | Restrictions | Data type | Description | 
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/CampaignOperation.md) | The Campaign selector for operations and list of operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V70/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V70">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V70/Campaign">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
        </operand>
        <operand>
          <campaignId>10002</campaignId>
        </operand>
        <operand>
          <campaignId>10003</campaignId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields in normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | This object is a container for campaign which includes operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V70/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V70">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1510827071599</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V70" xmlns:ns2="http://ss.yahooapis.jp/V70/Campaign">
      <ns2:rval>
        <ListReturnValue.Type>CampaignReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>set Standard Campaign with TargetSpendBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20301231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>20000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategyConfiguration>
              <ns2:biddingStrategyId>20001</ns2:biddingStrategyId>
              <ns2:biddingStrategyName>TargetSpendBiddingScheme.</ns2:biddingStrategyName>
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:biddingStrategySource>CAMPAIGN</ns2:biddingStrategySource>
              <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
                <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
                <ns2:bidCeiling>50000</ns2:bidCeiling>
                <ns2:spendTarget>0</ns2:spendTarget>
              </ns2:biddingScheme>
            </ns2:biddingStrategyConfiguration>
            <ns2:conversionOptimizerEligibility>DISABLE</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>ROTATE_INDEFINITELY</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>DONT_CARE</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>DONT_CARE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>DEACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:urlReviewData>
              <ns2:urlApprovalStatus>APPROVED</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignTrackId>100000002</ns2:campaignTrackId>
            <ns2:campaignName>set MobileApp(ANDROID) Campaign with PageOnePromotedBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20301231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>20000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategyConfiguration>
              <ns2:biddingStrategyId>20002</ns2:biddingStrategyId>
              <ns2:biddingStrategyName>PageOnePromotedBiddingScheme.</ns2:biddingStrategyName>
              <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
              <ns2:biddingStrategySource>CAMPAIGN</ns2:biddingStrategySource>
              <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PageOnePromotedBiddingScheme">
                <ns2:biddingStrategyType>PAGE_ONE_PROMOTED</ns2:biddingStrategyType>
                <ns2:bidCeiling>50000</ns2:bidCeiling>
                <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
                <ns2:bidChangesForRaisesOnly>ACTIVE</ns2:bidChangesForRaisesOnly>
                <ns2:raiseBidWhenBudgetConstrained>DEACTIVE</ns2:raiseBidWhenBudgetConstrained>
                <ns2:raiseBidWhenLowQualityScore>DEACTIVE</ns2:raiseBidWhenLowQualityScore>
              </ns2:biddingScheme>
            </ns2:biddingStrategyConfiguration>
            <ns2:conversionOptimizerEligibility>DISABLE</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>ROTATE_INDEFINITELY</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>DONT_CARE</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>DONT_CARE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>DEACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:campaignType>MOBILE_APP</ns2:campaignType>
            <ns2:appStore>ANDROID</ns2:appStore>
            <ns2:appId>201607221800792</ns2:appId>
            <ns2:urlReviewData>
              <ns2:urlApprovalStatus>NONE</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10003</ns2:campaignId>
            <ns2:campaignTrackId>100000003</ns2:campaignTrackId>
            <ns2:campaignName>set MobileApp(IOS) Campaign with ManualCpcBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20301231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>20000</ns2:amount>
              <ns2:deliveryMethod>STANDARD</ns2:deliveryMethod>
            </ns2:budget>
            <ns2:biddingStrategyConfiguration>
              <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
              <ns2:biddingStrategyName>ManualCpcBiddingScheme.</ns2:biddingStrategyName>
              <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              <ns2:biddingStrategySource>CAMPAIGN</ns2:biddingStrategySource>
              <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ManualCpcBiddingScheme">
                <ns2:biddingStrategyType>MANUAL_CPC</ns2:biddingStrategyType>
              </ns2:biddingScheme>
            </ns2:biddingStrategyConfiguration>
            <ns2:conversionOptimizerEligibility>DISABLE</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>ROTATE_INDEFINITELY</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>DONT_CARE</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>DONT_CARE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>DEACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:campaignType>MOBILE_APP</ns2:campaignType>
            <ns2:appStore>IOS</ns2:appStore>
            <ns2:appId>201608188643114</ns2:appId>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:urlReviewData>
              <ns2:urlApprovalStatus>APPROVED</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
