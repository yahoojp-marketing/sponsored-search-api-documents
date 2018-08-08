# CampaignService
CampaignService is to get, add, update, or remove campaigns.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/CampaignService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/CampaignService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201808/Campaign

#### Service Overview
Get, add, update, or remove campaigns.

#### Operation
Explains the operation which provides at CampaignService.

+ [get](#get)
+ [mutate(ADD)](#mutate-add)
+ [mutate(SET)](#mutate-set)
+ [mutate(REMOVE)](#mutate-remove)

#### Object
[Campaign](../data/Campaign)

## get
Gets information related to campaigns.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [CampaignSelector](../data/Campaign/CampaignSelector.md) | The campaign selector for operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <userStatuses>ACTIVE</userStatuses>
        <userStatuses>PAUSED</userStatuses>
        <biddingStrategyIds>20001</biddingStrategyIds>
        <biddingStrategyIds>20002</biddingStrategyIds>
        <biddingStrategyIds>20003</biddingStrategyIds>
        <biddingStrategyIds>20004</biddingStrategyIds>
        <biddingStrategyIds>20005</biddingStrategyIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>1000</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields in normal cases.

| Field | Data Type | Description |
|---|---|---|
| rval | [CampaignPage](../data/Campaign/CampaignPage.md) | Entry of acquired campaign. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1532514147169</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Campaign">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <Page.Type>CampaignPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>Standard Campaign with TargetSpendBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:conversionOptimizerEligibility>NOT_ENOUGH_CONVERSIONS</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>AREA_OF_INTENT</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
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
            <ns2:campaignName>MobileApp(ANDROID) Campaign with PageOnePromotedBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:conversionOptimizerEligibility>NOT_ENOUGH_CONVERSIONS</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>AREA_OF_INTENT</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
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
            <ns2:campaignName>MobileApp(IOS) Campaign with ManualCpcBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:conversionOptimizerEligibility>NOT_ENOUGH_CONVERSIONS</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>AREA_OF_INTENT</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
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
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignTrackId>100000004</ns2:campaignTrackId>
            <ns2:campaignName>DynamicAdsForSearchSetting Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:conversionOptimizerEligibility>ENABLE</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAdsForSearchSetting">
              <ns2:type>DYNAMIC_ADS_FOR_SEARCH_SETTING</ns2:type>
              <ns2:feedFolderIds>11111</ns2:feedFolderIds>
            </ns2:settings>
            <ns2:campaignType>DYNAMIC_ADS_FOR_SEARCH</ns2:campaignType>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Add campaign information.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/Campaign/CampaignOperation.md) | The Campaign selector for operations and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/Campaign">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignName>Standard Campaign with TargetSpendBiddingScheme.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <period>DAILY</period>
            <amount>10000</amount>
            <deliveryMethod>STANDARD</deliveryMethod>
          </budget>
          <biddingStrategyConfiguration>
            <biddingStrategyId>20001</biddingStrategyId>
          </biddingStrategyConfiguration>
          <adServingOptimizationStatus>OPTIMIZE</adServingOptimizationStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTargetTypeSetting">
            <type>GEO_TARGET_TYPE_SETTING</type>
            <positiveGeoTargetType>AREA_OF_INTENT</positiveGeoTargetType>
            <negativeGeoTargetType>LOCATION_OF_PRESENCE</negativeGeoTargetType>
          </settings>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <type>TARGET_LIST_SETTING</type>
            <targetAll>ACTIVE</targetAll>
          </settings>
          <campaignType>STANDARD</campaignType>
          <trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</trackingUrl>
          <customParameters>
            <parameters>
              <key>site</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id1</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id2</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
        </operand>
        <operand>
          <campaignName>MobileApp(ANDROID) Campaign with PageOnePromotedBiddingScheme.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <period>DAILY</period>
            <amount>10000</amount>
            <deliveryMethod>STANDARD</deliveryMethod>
          </budget>
          <biddingStrategyConfiguration>
            <biddingStrategyId>20002</biddingStrategyId>
          </biddingStrategyConfiguration>
          <adServingOptimizationStatus>OPTIMIZE</adServingOptimizationStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTargetTypeSetting">
            <type>GEO_TARGET_TYPE_SETTING</type>
            <positiveGeoTargetType>AREA_OF_INTENT</positiveGeoTargetType>
            <negativeGeoTargetType>LOCATION_OF_PRESENCE</negativeGeoTargetType>
          </settings>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <type>TARGET_LIST_SETTING</type>
            <targetAll>ACTIVE</targetAll>
          </settings>
          <campaignType>MOBILE_APP</campaignType>
          <appStore>ANDROID</appStore>
          <appId>201607221800792</appId>
        </operand>
        <operand>
          <campaignName>MobileApp(IOS) Campaign with ManualCpcBiddingScheme.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <period>DAILY</period>
            <amount>10000</amount>
            <deliveryMethod>STANDARD</deliveryMethod>
          </budget>
          <biddingStrategyConfiguration>
            <biddingStrategyType>MANUAL_CPC</biddingStrategyType>
          </biddingStrategyConfiguration>
          <adServingOptimizationStatus>OPTIMIZE</adServingOptimizationStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTargetTypeSetting">
            <type>GEO_TARGET_TYPE_SETTING</type>
            <positiveGeoTargetType>AREA_OF_INTENT</positiveGeoTargetType>
            <negativeGeoTargetType>LOCATION_OF_PRESENCE</negativeGeoTargetType>
          </settings>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <type>TARGET_LIST_SETTING</type>
            <targetAll>ACTIVE</targetAll>
          </settings>
          <campaignType>MOBILE_APP</campaignType>
          <appStore>IOS</appStore>
          <appId>201608188643114</appId>
          <trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</trackingUrl>
          <customParameters>
            <parameters>
              <key>site</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id1</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id2</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
        </operand>
        <operand>
          <campaignName>DynamicAdsForSearchSetting Campaign.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <startDate>20170101</startDate>
          <endDate>20371231</endDate>
          <budget>
            <period>DAILY</period>
            <amount>10000</amount>
            <deliveryMethod>STANDARD</deliveryMethod>
          </budget>
          <biddingStrategyConfiguration>
            <biddingStrategyType>MANUAL_CPC</biddingStrategyType>
          </biddingStrategyConfiguration>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DynamicAdsForSearchSetting">
            <type>DYNAMIC_ADS_FOR_SEARCH_SETTING</type>
            <feedFolderIds>11111</feedFolderIds>
          </settings>
          <campaignType>DYNAMIC_ADS_FOR_SEARCH</campaignType>
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
| rval | [CampaignReturnValue](../data/Campaign/CampaignReturnValue.md) | This object is a container for campaign information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1532514147780</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Campaign">
      <ns2:rval>
        <ListReturnValue.Type>CampaignReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>0</ns2:campaignTrackId>
            <ns2:campaignName>Standard Campaign with TargetSpendBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>AREA_OF_INTENT</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:campaignType>STANDARD</ns2:campaignType>
            <ns2:urlReviewData>
              <ns2:inReviewUrl>
                <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
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
              </ns2:inReviewUrl>
              <ns2:urlApprovalStatus>REVIEW</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10002</ns2:campaignId>
            <ns2:campaignTrackId>0</ns2:campaignTrackId>
            <ns2:campaignName>MobileApp(ANDROID) Campaign with PageOnePromotedBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>AREA_OF_INTENT</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
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
            <ns2:campaignTrackId>0</ns2:campaignTrackId>
            <ns2:campaignName>MobileApp(IOS) Campaign with ManualCpcBiddingScheme.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTargetTypeSetting">
              <ns2:type>GEO_TARGET_TYPE_SETTING</ns2:type>
              <ns2:positiveGeoTargetType>AREA_OF_INTENT</ns2:positiveGeoTargetType>
              <ns2:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns2:negativeGeoTargetType>
            </ns2:settings>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:type>TARGET_LIST_SETTING</ns2:type>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:campaignType>MOBILE_APP</ns2:campaignType>
            <ns2:appStore>IOS</ns2:appStore>
            <ns2:appId>201608188643114</ns2:appId>
            <ns2:urlReviewData>
              <ns2:inReviewUrl>
                <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
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
              </ns2:inReviewUrl>
              <ns2:urlApprovalStatus>REVIEW</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
          </ns2:campaign>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignTrackId>100000004</ns2:campaignTrackId>
            <ns2:campaignName>DynamicAdsForSearchSetting Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:conversionOptimizerEligibility>ENABLE</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAdsForSearchSetting">
              <ns2:type>DYNAMIC_ADS_FOR_SEARCH_SETTING</ns2:type>
              <ns2:feedFolderIds>11111</ns2:feedFolderIds>
            </ns2:settings>
            <ns2:campaignType>DYNAMIC_ADS_FOR_SEARCH</ns2:campaignType>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Updates the information related to campaigns.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/Campaign/CampaignOperation.md) | The Campaign selector for operations and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/Campaign">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <campaignName>set Standard Campaign with TargetSpendBiddingScheme.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <endDate>20301231</endDate>
          <budget>
            <amount>20000</amount>
          </budget>
          <adServingOptimizationStatus>ROTATE_INDEFINITELY</adServingOptimizationStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTargetTypeSetting">
            <type>GEO_TARGET_TYPE_SETTING</type>
            <positiveGeoTargetType>DONT_CARE</positiveGeoTargetType>
            <negativeGeoTargetType>DONT_CARE</negativeGeoTargetType>
          </settings>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <type>TARGET_LIST_SETTING</type>
            <targetAll>DEACTIVE</targetAll>
          </settings>
        </operand>
        <operand>
          <campaignId>10002</campaignId>
          <campaignName>set MobileApp(ANDROID) Campaign with PageOnePromotedBiddingScheme.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <endDate>20301231</endDate>
          <budget>
            <amount>20000</amount>
          </budget>
          <adServingOptimizationStatus>ROTATE_INDEFINITELY</adServingOptimizationStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTargetTypeSetting">
            <type>GEO_TARGET_TYPE_SETTING</type>
            <positiveGeoTargetType>DONT_CARE</positiveGeoTargetType>
            <negativeGeoTargetType>DONT_CARE</negativeGeoTargetType>
          </settings>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <type>TARGET_LIST_SETTING</type>
            <targetAll>DEACTIVE</targetAll>
          </settings>
        </operand>
        <operand>
          <campaignId>10003</campaignId>
          <campaignName>set MobileApp(IOS) Campaign with ManualCpcBiddingScheme.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <endDate>20301231</endDate>
          <budget>
            <amount>20000</amount>
          </budget>
          <adServingOptimizationStatus>ROTATE_INDEFINITELY</adServingOptimizationStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="GeoTargetTypeSetting">
            <type>GEO_TARGET_TYPE_SETTING</type>
            <positiveGeoTargetType>DONT_CARE</positiveGeoTargetType>
            <negativeGeoTargetType>DONT_CARE</negativeGeoTargetType>
          </settings>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <type>TARGET_LIST_SETTING</type>
            <targetAll>DEACTIVE</targetAll>
          </settings>
        </operand>
        <operand>
          <campaignId>10004</campaignId>
          <campaignName>set DynamicAdsForSearchSetting Campaign.</campaignName>
          <userStatus>ACTIVE</userStatus>
          <endDate>20301231</endDate>
          <budget>
            <amount>20000</amount>
          </budget>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="DynamicAdsForSearchSetting">
            <type>DYNAMIC_ADS_FOR_SEARCH_SETTING</type>
            <feedFolderIds>11111</feedFolderIds>
          </settings>
          <campaignType>DYNAMIC_ADS_FOR_SEARCH</campaignType>
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
| rval | [CampaignReturnValue](../data/Campaign/CampaignReturnValue.md) | This object is a container for campaign including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1532514147928</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Campaign">
      <ns2:rval>
        <ListReturnValue.Type>CampaignReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
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
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignTrackId>100000004</ns2:campaignTrackId>
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
            <ns2:conversionOptimizerEligibility>ENABLE</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAdsForSearchSetting">
              <ns2:type>DYNAMIC_ADS_FOR_SEARCH_SETTING</ns2:type>
              <ns2:feedFolderIds>11111</ns2:feedFolderIds>
            </ns2:settings>
            <ns2:campaignType>DYNAMIC_ADS_FOR_SEARCH</ns2:campaignType>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
Removes the inforamtion related to campaigns.

### Request
| Parameter | Restrictions | Data type | Description |
|---|---|---|---|
| operations | Req | [CampaignOperation](../data/Campaign/CampaignOperation.md) | The Campaign selector for operations and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/Campaign">
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
        <operand>
          <campaignId>10004</campaignId>
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
| rval | [CampaignReturnValue](../data/Campaign/CampaignReturnValue.md) | This object is a container for campaign which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/Campaign" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>Campaign</ns2:service>
      <ns2:requestTime>1532514148055</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Campaign">
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
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaign>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10004</ns2:campaignId>
            <ns2:campaignTrackId>100000004</ns2:campaignTrackId>
            <ns2:campaignName>DynamicAdsForSearchSetting Campaign.</ns2:campaignName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:servingStatus>SERVING</ns2:servingStatus>
            <ns2:startDate>20170101</ns2:startDate>
            <ns2:endDate>20371231</ns2:endDate>
            <ns2:budget>
              <ns2:period>DAILY</ns2:period>
              <ns2:amount>10000</ns2:amount>
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
            <ns2:conversionOptimizerEligibility>ENABLE</ns2:conversionOptimizerEligibility>
            <ns2:adServingOptimizationStatus>OPTIMIZE</ns2:adServingOptimizationStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:DynamicAdsForSearchSetting">
              <ns2:type>DYNAMIC_ADS_FOR_SEARCH_SETTING</ns2:type>
              <ns2:feedFolderIds>11111</ns2:feedFolderIds>
            </ns2:settings>
            <ns2:campaignType>DYNAMIC_ADS_FOR_SEARCH</ns2:campaignType>
          </ns2:campaign>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
