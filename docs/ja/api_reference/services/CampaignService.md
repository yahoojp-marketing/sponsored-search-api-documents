# CampaignService
CampaignServiceでは、キャンペーンに関する情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/CampaignService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/CampaignService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
キャンペーンに関する情報の取得および追加・更新・削除を行います。

#### 操作
CampaignServiceで提供される操作を説明します。

## get
キャンペーンに関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [CampaignSelector](../data/CampaignSelector.md) | 操作の対象とするキャンペーンの情報です。 | 

##### ＜リクエストサンプル＞
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

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignPage](../data/CampaignPage.md) | 取得されるキャンペーンに関するエントリーです。 | 

##### ＜レスポンスサンプル＞
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
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>CampaignPage</ns1:Page.Type>
        <!-- V5.3までに登録したキャンペーン -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000001</ns1:campaignId>
            <ns1:campaignTrackId>3000000001</ns1:campaignTrackId>
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
            <ns1:campaignId>2000000002</ns1:campaignId>
            <ns1:campaignTrackId>3000000002</ns1:campaignTrackId>
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
            <ns1:campaignId>2000000003</ns1:campaignId>
            <ns1:campaignTrackId>3000000003</ns1:campaignTrackId>
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
            <ns1:appId>jp.yahooapis.ss.V6.sampleApplication</ns1:appId>
          </ns1:campaign>
        </ns1:values>
        <!-- V6.0以降に登録したキャンペーン -->
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
            <ns1:campaignType>STANDARD</ns1:campaignType>
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
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000004</ns1:campaignId>
            <ns1:campaignTrackId>3000000006</ns1:campaignTrackId>
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
            <ns1:urlReviewData>
              <ns1:disapprovalReviewUrl>
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
              </ns1:disapprovalReviewUrl>
              <ns1:urlApprovalStatus>DISAPPROVED</ns1:urlApprovalStatus>
              <ns1:disapprovalReasonCodes>1001</ns1:disapprovalReasonCodes>
              <ns1:disapprovalReasonCodes>1002</ns1:disapprovalReasonCodes>
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
            <ns1:campaignType>MOBILE_APP</ns1:campaignType>
            <ns1:appStore>IOS</ns1:appStore>
            <ns1:appId>100000000000000</ns1:appId>
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
              <ns1:urlApprovalStatus>APPROVED_WITH_REVIEW</ns1:urlApprovalStatus>
            </ns1:urlReviewData>
          </ns1:campaign>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
キャンペーンを追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignOperation](../data/CampaignOperation.md) | 操作の対象となるキャンペーンの情報および操作の内容を表します。 | 

##### ＜リクエストサンプル＞
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
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <!-- Standard Campaign -->
        <ns1:operand>
          <ns1:campaignName>STANDARD_MANUAL_CPC_${__time(YMDHMS,rTime)}_${__Random(1000000,9999999)}</ns1:campaignName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:startDate>${__time(YMD,rTime)}</ns1:startDate>
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
        </ns1:operand>
        <!-- Mobile APP Campaign(IOS Only) -->
        <ns1:operand>
          <ns1:campaignName>IOS_MANUAL_CPC_${__time(YMDHMS,rTime)}_${__Random(1000000,9999999)}</ns1:campaignName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:startDate>${__time(YMD,rTime)}</ns1:startDate>
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
          <ns1:campaignType>MOBILE_APP</ns1:campaignType>
          <ns1:appStore>IOS</ns1:appStore>
          <ns1:appId>${__time(YMD,rTime)}${__Random(1000000,9999999)}</ns1:appId>
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
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | 操作結果を含むキャンペーンに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
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
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <!-- Standard Campaign -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>878935</ns1:campaignId>
            <ns1:campaignName>STANDARD_MANUAL_CPC_20151126-172421_8817360</ns1:campaignName>
            <ns1:userStatus>ACTIVE</ns1:userStatus>
            <ns1:servingStatus>SERVING</ns1:servingStatus>
            <ns1:startDate>20151126</ns1:startDate>
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
            <ns1:campaignType>STANDARD</ns1:campaignType>
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
        <!-- Mobile APP Campaign(IOS Only) -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>878936</ns1:campaignId>
            <ns1:campaignName>IOS_MANUAL_CPC_20151126-172425_2884194</ns1:campaignName>
            <ns1:userStatus>ACTIVE</ns1:userStatus>
            <ns1:servingStatus>SERVING</ns1:servingStatus>
            <ns1:startDate>20151126</ns1:startDate>
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
            <ns1:campaignType>MOBILE_APP</ns1:campaignType>
            <ns1:appStore>IOS</ns1:appStore>
            <ns1:appId>201511261169467</ns1:appId>
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
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
キャンペーンを更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignOperation](../data/CampaignOperation.md) | 操作の対象となるキャンペーンの情報および操作の内容を表します。 | 

##### ＜リクエストサンプル＞
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
        <!-- Standard Campaign -->
        <ns1:operand>
          <ns1:campaignId>200000001</ns1:campaignId>
          <ns1:campaignName>STANDARD_MANUAL_CPC_${__time(YMDHMS,rTime)}_${__Random(1000000,9999999)}</ns1:campaignName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:startDate>${__time(YMD,rTime)}</ns1:startDate>
          <ns1:endDate>20361231</ns1:endDate>
          <ns1:budget>
            <ns1:period>DAILY</ns1:period>
            <ns1:amount>10000</ns1:amount>
            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
          </ns1:budget>
          <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
          <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
            <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
            <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
            <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
          </ns1:settings>
          <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:trackingUrl>
          <ns1:customParameters>
            <ns1:isRemove>FALSE</ns1:isRemove>
            <ns1:parameters>
              <ns1:key>site</ns1:key>
              <ns1:value>mysite</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id1</ns1:key>
              <ns1:value>5678</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id2</ns1:key>
              <ns1:value>jFj903Hng8e</ns1:value>
            </ns1:parameters>
          </ns1:customParameters>
       </ns1:operand>
        <!-- Mobile APP Campaign(IOS Only) -->
        <ns1:operand>
          <ns1:campaignId>200000002</ns1:campaignId>
          <ns1:campaignName>STANDARD_MANUAL_CPC_${__time(YMDHMS,rTime)}_${__Random(1000000,9999999)}</ns1:campaignName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:startDate>${__time(YMD,rTime)}</ns1:startDate>
          <ns1:endDate>20361231</ns1:endDate>
          <ns1:budget>
            <ns1:period>DAILY</ns1:period>
            <ns1:amount>10000</ns1:amount>
            <ns1:deliveryMethod>STANDARD</ns1:deliveryMethod>
          </ns1:budget>
          <ns1:adServingOptimizationStatus>OPTIMIZE</ns1:adServingOptimizationStatus>
          <ns1:settings xsi:type="ns1:GeoTargetTypeSetting">
            <ns1:type>GEO_TARGET_TYPE_SETTING</ns1:type>
            <ns1:positiveGeoTargetType>DONT_CARE</ns1:positiveGeoTargetType>
            <ns1:negativeGeoTargetType>LOCATION_OF_PRESENCE</ns1:negativeGeoTargetType>
          </ns1:settings>
          <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:trackingUrl>
          <ns1:customParameters>
            <ns1:isRemove>FALSE</ns1:isRemove>
            <ns1:parameters>
              <ns1:key>site</ns1:key>
              <ns1:value>mysite</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id1</ns1:key>
              <ns1:value>5678</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id2</ns1:key>
              <ns1:value>jFj903Hng8e</ns1:value>
            </ns1:parameters>
          </ns1:customParameters>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | 操作結果を含むキャンペーンに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
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
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <!-- Standard Campaign -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>878935</ns1:campaignId>
            <ns1:campaignName>STANDARD_MANUAL_CPC_20151126-172421_8817360</ns1:campaignName>
            <ns1:userStatus>ACTIVE</ns1:userStatus>
            <ns1:servingStatus>SERVING</ns1:servingStatus>
            <ns1:startDate>20151126</ns1:startDate>
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
            <ns1:campaignType>STANDARD</ns1:campaignType>
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
            <ns1:urlReviewData>
              <ns1:inReviewUrl>
                <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:trackingUrl>
                <ns1:parameters>
                  <ns1:key>site</ns1:key>
                  <ns1:value>mysite</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id1</ns1:key>
                  <ns1:value>5678</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id2</ns1:key>
                  <ns1:value>jFj903Hng8e</ns1:value>
                </ns1:parameters>
              </ns1:inReviewUrl>
              <ns1:urlApprovalStatus>APPROVED_WITH_REVIEW</ns1:urlApprovalStatus>
            </ns1:urlReviewData>
          </ns1:campaign>
        </ns1:values>
        <!-- Mobile APP Campaign(IOS Only) -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>878936</ns1:campaignId>
            <ns1:campaignName>IOS_MANUAL_CPC_20151126-172425_2884194</ns1:campaignName>
            <ns1:userStatus>ACTIVE</ns1:userStatus>
            <ns1:servingStatus>SERVING</ns1:servingStatus>
            <ns1:startDate>20151126</ns1:startDate>
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
            <ns1:campaignType>MOBILE_APP</ns1:campaignType>
            <ns1:appStore>IOS</ns1:appStore>
            <ns1:appId>201511261169467</ns1:appId>
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
            <ns1:urlReviewData>
              <ns1:inReviewUrl>
                <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:trackingUrl>
                <ns1:parameters>
                  <ns1:key>site</ns1:key>
                  <ns1:value>mysite</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id1</ns1:key>
                  <ns1:value>5678</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id2</ns1:key>
                  <ns1:value>jFj903Hng8e</ns1:value>
                </ns1:parameters>
              </ns1:inReviewUrl>
              <ns1:urlApprovalStatus>APPROVED_WITH_REVIEW</ns1:urlApprovalStatus>
            </ns1:urlReviewData>
          </ns1:campaign>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
キャンペーンを削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignOperation](../data/CampaignOperation.md) | 操作の対象となるキャンペーンの情報および操作の内容を表します。 | 

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
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

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignReturnValue](../data/CampaignReturnValue.md) | 操作結果を含むキャンペーンに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
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
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>CampaignReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <!-- Standard Campaign -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>878935</ns1:campaignId>
            <ns1:campaignName>STANDARD_MANUAL_CPC_20151126-172421_8817360</ns1:campaignName>
            <ns1:userStatus>ACTIVE</ns1:userStatus>
            <ns1:servingStatus>SERVING</ns1:servingStatus>
            <ns1:startDate>20151126</ns1:startDate>
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
            <ns1:campaignType>STANDARD</ns1:campaignType>
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
            <ns1:urlReviewData>
              <ns1:inReviewUrl>
                <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:trackingUrl>
                <ns1:parameters>
                  <ns1:key>site</ns1:key>
                  <ns1:value>mysite</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id1</ns1:key>
                  <ns1:value>5678</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id2</ns1:key>
                  <ns1:value>jFj903Hng8e</ns1:value>
                </ns1:parameters>
              </ns1:inReviewUrl>
              <ns1:urlApprovalStatus>APPROVED_WITH_REVIEW</ns1:urlApprovalStatus>
            </ns1:urlReviewData>
          </ns1:campaign>
        </ns1:values>
        <!-- Mobile APP Campaign(IOS Only) -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:campaign>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>878936</ns1:campaignId>
            <ns1:campaignName>IOS_MANUAL_CPC_20151126-172425_2884194</ns1:campaignName>
            <ns1:userStatus>ACTIVE</ns1:userStatus>
            <ns1:servingStatus>SERVING</ns1:servingStatus>
            <ns1:startDate>20151126</ns1:startDate>
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
            <ns1:campaignType>MOBILE_APP</ns1:campaignType>
            <ns1:appStore>IOS</ns1:appStore>
            <ns1:appId>201511261169467</ns1:appId>
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
            <ns1:urlReviewData>
              <ns1:inReviewUrl>
                <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:trackingUrl>
                <ns1:parameters>
                  <ns1:key>site</ns1:key>
                  <ns1:value>mysite</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id1</ns1:key>
                  <ns1:value>5678</ns1:value>
                </ns1:parameters>
                <ns1:parameters>
                  <ns1:key>id2</ns1:key>
                  <ns1:value>jFj903Hng8e</ns1:value>
                </ns1:parameters>
              </ns1:inReviewUrl>
              <ns1:urlApprovalStatus>APPROVED_WITH_REVIEW</ns1:urlApprovalStatus>
            </ns1:urlReviewData>
          </ns1:campaign>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
