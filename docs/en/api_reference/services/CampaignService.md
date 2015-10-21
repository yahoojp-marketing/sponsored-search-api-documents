# CampaignService
CampaignService is to get, add, update, or delete campaigns.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/CampaignService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/CampaignService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V5

#### Overview
Get, add, update, or delete campaigns.

#### Operation
Explains the operation which provides at CampaignService.

## get

### Request
Gets information related to campaigns.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [CampaignSelector](../data/CampaignSelector.md) | Campaign information relate to the operations to apply. | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignPage](../data/CampaignPage.md) | The acquired entry related campaign. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
        <ns1:totalNumEntries>9</ns1:totalNumEntries>
        <ns1:Page.Type>CampaignPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>1000000001</ns1:campaignId>
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
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>1000000002</ns1:campaignId>
            <ns1:campaignName>campaign name2</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20101201</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyType>BUDGET_OPTIMIZER</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:BudgetOptimizerBiddingScheme">
                <ns1:biddingStrategyType>BUDGET_OPTIMIZER</ns1:biddingStrategyType>
                <ns1:bidCeiling>50000</ns1:bidCeiling>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000001</ns1:campaignId>
            <ns1:campaignName>Sample campaign ManualCPC</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20140702</ns1:startDate>
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
            <ns1:conversionOptimizerEligibility>NOT_ENOUGH_CONVERSIONS</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000002</ns1:campaignId>
            <ns1:campaignName>Sample campaign EnhancedCpcBidding</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20140702</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyId>10000000001</ns1:biddingStrategyId>
              <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
              <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000003</ns1:campaignId>
            <ns1:campaignName>Sample campaign PageOnePromotedBidding</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20140702</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyId>10000000002</ns1:biddingStrategyId>
              <ns1:biddingStrategyName>Sample bidding PageOnePromotedBidding</ns1:biddingStrategyName>
              <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                <ns1:bidCeiling>10000</ns1:bidCeiling>
                <ns1:bidMultiplier>10.00</ns1:bidMultiplier>
                <ns1:bidChangesForRaisesOnly>ACTIVE</ns1:bidChangesForRaisesOnly>
                <ns1:raiseBidWhenBudgetConstrained>DEACTIVE</ns1:raiseBidWhenBudgetConstrained>
                <ns1:raiseBidWhenLowQualityScore>DEACTIVE</ns1:raiseBidWhenLowQualityScore>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000004</ns1:campaignId>
            <ns1:campaignName>Sample campaign TargetCpaBidding</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20140702</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyId>10000000003</ns1:biddingStrategyId>
              <ns1:biddingStrategyName>Sample bidding TargetCpaBidding</ns1:biddingStrategyName>
              <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:TargetCpaBiddingScheme">
                <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                <ns1:targetCpa>100</ns1:targetCpa>
                <ns1:bidCeiling>10000</ns1:bidCeiling>
                <ns1:bidFloor>0</ns1:bidFloor>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000005</ns1:campaignId>
            <ns1:campaignName>Sample campaign TargetSpendBidding</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20140702</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyId>10000000004</ns1:biddingStrategyId>
              <ns1:biddingStrategyName>Sample bidding TargetSpendBidding</ns1:biddingStrategyName>
              <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                <ns1:bidCeiling>10000</ns1:bidCeiling>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>CONVERSION_TRACKING_NOT_ENABLED</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000006</ns1:campaignId>
            <ns1:campaignName>Sample campaign TargetRoasBidding</ns1:campaignName>
            <ns1:userStatus>PAUSED</ns1:userStatus>
            <ns1:servingStatus>PENDING</ns1:servingStatus>
            <ns1:startDate>20140702</ns1:startDate>
            <ns1:endDate>20141231</ns1:endDate>
            <ns1:budget>
              <ns1:period>DAILY</ns1:period>
              <ns1:amount>10000</ns1:amount>
              <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
            </ns1:budget>
            <ns1:biddingStrategyConfiguration>
              <ns1:biddingStrategyId>10000000005</ns1:biddingStrategyId>
              <ns1:biddingStrategyName>Sample bidding TargetRoasBidding</ns1:biddingStrategyName>
              <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
              <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
              <ns1:biddingScheme xsi:type="ns1:TargetRoasBiddingScheme">
                <ns1:biddingStrategyType>TARGET_ROAS</ns1:biddingStrategyType>
                <ns1:targetRoas>0.01</ns1:targetRoas>
                <ns1:bidCeiling>10000</ns1:bidCeiling>
                <ns1:bidFloor>5000</ns1:bidFloor>
              </ns1:biddingScheme>
            </ns1:biddingStrategyConfiguration>
            <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
            <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
            <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
              <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
              <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
              <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
            </ns1:settings>
            <ns1:campaignType>STANDARD</ns1:campaignType>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>3000000001</ns1:campaignId>
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
            <ns1:campaignType>MOBILE_APP</ns1:campaignType>
            <ns1:appStore>IOS</ns1:appStore>
            <ns1:appId>100000000000000</ns1:appId>
          </ns1:campaign>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>3000000002</ns1:campaignId>
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
            <ns1:campaignType>MOBILE_APP</ns1:campaignType>
            <ns1:appStore>ANDROID</ns1:appStore>
            <ns1:appId>jp.yahooapis.ss.V5.sampleApplication</ns1:appId>
          </ns1:campaign>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (Failure of Bidding)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:totalNumEntries>9</ns1:totalNumEntries>
            <ns1:Page.Type>CampaignPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000007</ns1:campaignId>
                  <ns1:campaignName>Sample campaign EnhancedCpcBidding</ns1:campaignName>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:servingStatus>PENDING</ns1:servingStatus>
                  <ns1:startDate>20140702</ns1:startDate>
                  <ns1:endDate>20141231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                        <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:biddingStrategyFailedReason>BIDDING_STRATEGY_CANNOT_BE_OVERRIDDEN</ns1:biddingStrategyFailedReason>
                  <ns1:failedBiddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                        <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                  </ns1:failedBiddingStrategyConfiguration>
                  <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
                  </ns1:settings>
               </ns1:campaign>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000010</ns1:campaignId>
                  <ns1:campaignName>Sample campaign TargetSpendBidding</ns1:campaignName>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:servingStatus>PENDING</ns1:servingStatus>
                  <ns1:startDate>20140702</ns1:startDate>
                  <ns1:endDate>20141231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000004</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding TargetSpendBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                        <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                        <ns1:bidCeiling>10000</ns1:bidCeiling>
                     </ns1:biddingScheme>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:biddingStrategyFailedReason>CONVERSION_TRACKING_NOT_ENABLED</ns1:biddingStrategyFailedReason>
                  <ns1:failedBiddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000003</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding TargetCpaBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:TargetCpaBiddingScheme">
                        <ns1:biddingStrategyType>TARGET_CPA</ns1:biddingStrategyType>
                        <ns1:targetCpa>100</ns1:targetCpa>
                        <ns1:bidCeiling>10000</ns1:bidCeiling>
                        <ns1:bidFloor>0</ns1:bidFloor>
                     </ns1:biddingScheme>
                  </ns1:failedBiddingStrategyConfiguration>
                  <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
                  </ns1:settings>
               </ns1:campaign>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
### Request
Add campaigns.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/CampaignOperation.md) | Operation elements for campaign information. | 

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
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>00000001</ns1:accountId>
                <!--ManualCPC-->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignName>Sample campaign ManualCPC</ns1:campaignName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                    <ns1:startDate>20140702</ns1:startDate>
                    <ns1:endDate>20141231</ns1:endDate>
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
                    </ns1:settings>
                </ns1:operand>
                <!--EnhancedCpcBidding-->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignName>Sample campaign EnhancedCpcBidding</ns1:campaignName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                    <ns1:startDate>20140702</ns1:startDate>
                    <ns1:endDate>20141231</ns1:endDate>
                    <ns1:budget>
                        <ns1:period>DAILY</ns1:period>
                        <ns1:amount>10000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyId>00000001</ns1:biddingStrategyId>
                    </ns1:biddingStrategyConfiguration>
                    <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                    <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                      <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                      <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                      <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                    </ns1:settings>
                </ns1:operand>
                <!--PageOnePromotedBidding-->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignName>Sample campaign PageOnePromotedBidding</ns1:campaignName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                    <ns1:startDate>20140702</ns1:startDate>
                    <ns1:endDate>20141231</ns1:endDate>
                    <ns1:budget>
                        <ns1:period>DAILY</ns1:period>
                        <ns1:amount>10000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyId>00000002</ns1:biddingStrategyId>
                    </ns1:biddingStrategyConfiguration>
                    <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                    <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                      <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                      <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                      <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                    </ns1:settings>
                </ns1:operand>
                <!--TargetSpendBidding-->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignName>Sample campaign TargetSpendBidding</ns1:campaignName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                    <ns1:startDate>20140702</ns1:startDate>
                    <ns1:endDate>20141231</ns1:endDate>
                    <ns1:budget>
                        <ns1:period>DAILY</ns1:period>
                        <ns1:amount>10000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyId>00000004</ns1:biddingStrategyId>
                    </ns1:biddingStrategyConfiguration>
                    <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                    <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                      <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                      <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                      <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                    </ns1:settings>
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
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | Container for campaign information including operation results. | 

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
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
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000006</ns1:campaignId>
                  <ns1:campaignName>Sample campaign ManualCPC</ns1:campaignName>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:servingStatus>PENDING</ns1:servingStatus>
                  <ns1:startDate>20140702</ns1:startDate>
                  <ns1:endDate>20141231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000000</ns1:amount>
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
               </ns1:campaign>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000007</ns1:campaignId>
                  <ns1:campaignName>Sample campaign EnhancedCpcBidding</ns1:campaignName>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:startDate>20140702</ns1:startDate>
                  <ns1:endDate>20141231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000001</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                        <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:conversionOptimizerEligibility>DISABLE</ns1:conversionOptimizerEligibility>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                  </ns1:settings>
               </ns1:campaign>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000008</ns1:campaignId>
                  <ns1:campaignName>Sample campaign PageOnePromotedBidding</ns1:campaignName>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:startDate>20140702</ns1:startDate>
                  <ns1:endDate>20141231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000002</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding PageOnePromotedBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
　                   <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                        <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                        <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                        <ns1:bidCeiling>10000</ns1:bidCeiling>
                        <ns1:bidMultiplier>10.00</ns1:bidMultiplier>
                        <ns1:bidChangesForRaisesOnly>ACTIVE</ns1:bidChangesForRaisesOnly>
                        <ns1:raiseBidWhenBudgetConstrained>DEACTIVE</ns1:raiseBidWhenBudgetConstrained>
                        <ns1:raiseBidWhenLowQualityScore>DEACTIVE</ns1:raiseBidWhenLowQualityScore>
                     </ns1:biddingScheme>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:conversionOptimizerEligibility>DISABLE</ns1:conversionOptimizerEligibility>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                  </ns1:settings>
               </ns1:campaign>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaign>
                  <ns1:accountId>00000001</ns1:accountId>
                  <ns1:campaignId>00000010</ns1:campaignId>
                  <ns1:campaignName>Sample campaign TargetSpendBidding</ns1:campaignName>
                  <ns1:userStatus>PAUSED</ns1:userStatus>
                  <ns1:startDate>20140702</ns1:startDate>
                  <ns1:endDate>20141231</ns1:endDate>
                  <ns1:budget>
                     <ns1:period>DAILY</ns1:period>
                     <ns1:amount>10000</ns1:amount>
                     <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                  </ns1:budget>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>00000004</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding TargetSpendBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
　                   <ns1:biddingScheme xsi:type="ns1:TargetSpendBiddingScheme">
                        <ns1:biddingStrategyType>TARGET_SPEND</ns1:biddingStrategyType>
                        <ns1:bidCeiling>10000</ns1:bidCeiling>
                     </ns1:biddingScheme>
                  </ns1:biddingStrategyConfiguration>
                  <ns1:conversionOptimizerEligibility>DISABLE</ns1:conversionOptimizerEligibility>
                  <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                  <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                     <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                     <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                     <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE
</ns1:negativeGeoTargetType>
                  </ns1:settings>
               </ns1:campaign>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
### Request
Updates campaigns.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/CampaignOperation.md) | Operation elements for campaign information. | 

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
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign001</ns1:campaignName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                    <ns1:budget>
                        <ns1:period>DAILY</ns1:period>
                        <ns1:amount>1000000</ns1:amount>
                        <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                    </ns1:budget>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                    </ns1:biddingStrategyConfiguration>
                    <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                      <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                      <ns1:positiveGeoTargetType>AREA_OF_INTENT</ns1:positiveGeoTargetType>
                      <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                    </ns1:settings>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>2000000002</ns1:campaignId>
                    <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Change to ManualCPC)
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
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>1000000003</ns1:campaignId>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                    </ns1:biddingStrategyConfiguration>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>2000000002</ns1:campaignId>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                    </ns1:biddingStrategyConfiguration>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Change to Auto bidding)
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
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>1000000003</ns1:campaignId>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyId>10000000001</ns1:biddingStrategyId>
                    </ns1:biddingStrategyConfiguration>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>2000000002</ns1:campaignId>
                    <ns1:biddingStrategyConfiguration>
                        <ns1:biddingStrategyId>10000000002</ns1:biddingStrategyId>
                    </ns1:biddingStrategyConfiguration>
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
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | Container for campaign information including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
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
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign001</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20101201</ns1:startDate>
                        <ns1:endDate>20101231</ns1:endDate>
                        <ns1:budget>
                            <ns1:period>DAILY</ns1:period>
                            <ns1:amount>10000000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategyConfiguration>
                            <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                            <ns1:biddingScheme xsi:type="ns1:ManualCpcBiddingScheme">
                               <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                            </ns1:biddingScheme>
                        </ns1:biddingStrategyConfiguration>
                        <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                        <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                        <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                          <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                          <ns1:positiveGeoTargetType>AREA_OF_INTENT</ns1:positiveGeoTargetType>
　　                      <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
                        </ns1:settings>
                   </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>2000000002</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20140702</ns1:startDate>
                        <ns1:endDate>20141231</ns1:endDate>
                        <ns1:budget>
                            <ns1:period>DAILY</ns1:period>
                            <ns1:amount>10000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategyConfiguration>
                            <ns1:biddingStrategyId>10000000001</ns1:biddingStrategyId>
                            <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
                            <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                            <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                            <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                               <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                            </ns1:biddingScheme>
                        </ns1:biddingStrategyConfiguration>
                        <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                        <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                        <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                            <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                            <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                            <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
                        </ns1:settings>
                   </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (Change to ManualCPC)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
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
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:campaignName>Sample campaign3</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20101201</ns1:startDate>
                        <ns1:endDate>20101231</ns1:endDate>
                        <ns1:budget>
                            <ns1:period>DAILY</ns1:period>
                            <ns1:amount>10000000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategyConfiguration>
                            <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
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
                   </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>2000000002</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20140702</ns1:startDate>
                        <ns1:endDate>20141231</ns1:endDate>
                        <ns1:budget>
                            <ns1:period>DAILY</ns1:period>
                            <ns1:amount>10000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategyConfiguration>
                            <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
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
                   </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (Change to Auto bidding)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
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
                        <ns1:campaignId>1000000003</ns1:campaignId>
                        <ns1:campaignName>Sample campaign3</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20101201</ns1:startDate>
                        <ns1:endDate>20101231</ns1:endDate>
                        <ns1:budget>
                            <ns1:period>DAILY</ns1:period>
                            <ns1:amount>10000000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategyConfiguration>
                            <ns1:biddingStrategyId>10000000001</ns1:biddingStrategyId>
                            <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
                            <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                            <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                            <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                               <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                            </ns1:biddingScheme>
                        </ns1:biddingStrategyConfiguration>
                        <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                        <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                        <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                            <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                            <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                            <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
                        </ns1:settings>
                   </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>2000000002</ns1:campaignId>
                        <ns1:campaignName>Modify sample campaign002</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>PENDING</ns1:servingStatus>
                        <ns1:startDate>20140702</ns1:startDate>
                        <ns1:endDate>20141231</ns1:endDate>
                        <ns1:budget>
                            <ns1:period>DAILY</ns1:period>
                            <ns1:amount>10000</ns1:amount>
                            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                        <ns1:biddingStrategyConfiguration>
                            <ns1:biddingStrategyId>10000000002</ns1:biddingStrategyId>
                            <ns1:biddingStrategyName>Sample bidding PageOnePromotedBidding</ns1:biddingStrategyName>
                            <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                            <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
　                          <ns1:biddingScheme xsi:type="ns1:PageOnePromotedBiddingScheme">
                                <ns1:biddingStrategyType>PAGE_ONE_PROMOTED</ns1:biddingStrategyType>
                                <ns1:targetPositionType>PAGE_ONE</ns1:targetPositionType>
                                <ns1:bidCeiling>10000</ns1:bidCeiling>
                                <ns1:bidMultiplier>10.00</ns1:bidMultiplier>
                                <ns1:bidChangesForRaisesOnly>ACTIVE</ns1:bidChangesForRaisesOnly>
                                <ns1:raiseBidWhenBudgetConstrained>DEACTIVE</ns1:raiseBidWhenBudgetConstrained>
                                <ns1:raiseBidWhenLowQualityScore>DEACTIVE</ns1:raiseBidWhenLowQualityScore>
                            </ns1:biddingScheme>
                        </ns1:biddingStrategyConfiguration>
                        <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                        <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                        <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                            <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                            <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
                            <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
                        </ns1:settings>
                   </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
### Request
Delete campaigns.

| Fileld | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/CampaignOperation.md) | Operation elements for campaign  information. | 

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
                <ns1:operand>
　　　　　　　　　　<ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                </ns1:operand>
                <ns1:operand>
　　　　　　　　　　<ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
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
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | Container for campaign information including operation results. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>LYNKS_20120502192120_unified更新</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20120502</ns1:startDate>
                        <ns1:endDate>20371231</ns1:endDate>
                        <ns1:budget>
                          <ns1:period>DAILY</ns1:period>
                          <ns1:amount>10000</ns1:amount>
                          <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                  　　　<ns1:biddingStrategyConfiguration>
                          <ns1:biddingStrategyType>BUDGET_OPTIMIZER</ns1:biddingStrategyType>
                          <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                          <ns1:biddingScheme xsi:type="ns1:BudgetOptimizerBiddingScheme">
                             <ns1:biddingStrategyType>BUDGET_OPTIMIZER</ns1:biddingStrategyType>
                             <ns1:bidCeiling>50000</ns1:bidCeiling>
                          </ns1:biddingScheme>
                        </ns1:biddingStrategyConfiguration>
                        <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                        <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                        <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                          <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                          <ns1:positiveGeoTargetType>LOCATION_OF_PRESENCE</ns1:positiveGeoTargetType>
                          <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
                        </ns1:settings>
                    </ns1:campaign>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaign>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>LYNKS_20120502192120_更新</ns1:campaignName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:servingStatus>SERVING</ns1:servingStatus>
                        <ns1:startDate>20120502</ns1:startDate>
                        <ns1:endDate>20371231</ns1:endDate>
                        <ns1:budget>
                          <ns1:period>DAILY</ns1:period>
                          <ns1:amount>10000</ns1:amount>
                          <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
                        </ns1:budget>
                  　　　<ns1:biddingStrategyConfiguration>
                          <ns1:biddingStrategyType>BUDGET_OPTIMIZER</ns1:biddingStrategyType>
                          <ns1:biddingStrategySource>CAMPAIGN</ns1:biddingStrategySource>
                          <ns1:biddingScheme xsi:type="ns1:BudgetOptimizerBiddingScheme">
                             <ns1:biddingStrategyType>BUDGET_OPTIMIZER</ns1:biddingStrategyType>
                             <ns1:bidCeiling>50000</ns1:bidCeiling>
                          </ns1:biddingScheme>
                        </ns1:biddingStrategyConfiguration>
                        <ns1:conversionOptimizerEligibility>ENABLE</ns1:conversionOptimizerEligibility>
                        <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
                        <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
                          <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
                          <ns1:positiveGeoTargetType>LOCATION_OF_PRESENCE</ns1:positiveGeoTargetType>
                          <ns1:negativeGeoTargetType>DONT_CARE</ns1:negativeGeoTargetType>
                        </ns1:settings>
                    </ns1:campaign>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
