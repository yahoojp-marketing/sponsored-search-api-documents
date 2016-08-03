# AdGroupService
AdGroupServiceでは、広告グループに関する情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
広告グループに関する情報の取得および追加・更新・削除を行います。

#### 操作
AdGroupServiceで提供される操作を説明します。

## get
広告グループに関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupSelector](../data/AdGroupSelector.md) | 操作の対象とする広告グループです。 | 

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
        <ns1:campaignIds>100000007</ns1:campaignIds>
        <ns1:adGroupIds>100000001</ns1:adGroupIds>
        <ns1:adGroupIds>100000002</ns1:adGroupIds>
        <ns1:adGroupIds>100000003</ns1:adGroupIds>
        <ns1:userStatuses>ACTIVE</ns1:userStatuses>
        <ns1:userStatuses>PAUSED</ns1:userStatuses>
        <ns1:biddingStrategyIds>100000001</ns1:biddingStrategyIds>
        <ns1:biddingStrategyIds>100000002</ns1:biddingStrategyIds>
        <ns1:biddingStrategyIds>100000003</ns1:biddingStrategyIds>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupPage](../data/AdGroupPage.md) | 取得される広告グループのエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupService</ns1:service>
      <ns1:remainingQuota>49992</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.9104</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>5</ns1:totalNumEntries>
        <ns1:Page.Type>AdGroupPage</ns1:Page.Type>
        <!-- V5.3までに登録した広告グループ -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000001</ns1:campaignId>
            <ns1:campaignTrackId>1111111111</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000001</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222221</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>DEACTIVE</ns1:targetAll>
            </ns1:settings>
          </ns1:adGroup>
        </ns1:values>
        <!-- V6.0以降に登録した広告グループ -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000002</ns1:campaignId>
            <ns1:campaignTrackId>1111111112</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000002</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222222</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>DEACTIVE</ns1:targetAll>
            </ns1:settings>
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
          </ns1:adGroup>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000003</ns1:campaignId>
            <ns1:campaignTrackId>1111111113</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000003</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222223</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>DEACTIVE</ns1:targetAll>
            </ns1:settings>
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
          </ns1:adGroup>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000004</ns1:campaignId>
            <ns1:campaignTrackId>1111111114</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000004</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222224</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>DEACTIVE</ns1:targetAll>
            </ns1:settings>
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
          </ns1:adGroup>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000005</ns1:campaignId>
            <ns1:campaignTrackId>1111111115</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000005</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222225</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>DEACTIVE</ns1:targetAll>
            </ns1:settings>
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
          </ns1:adGroup>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
広告グループを追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 | 

##### ＜リクエストサンプル＞
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
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:campaignId>2000000001</ns1:campaignId>
          <ns1:adGroupName>sample adgroup</ns1:adGroupName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:biddingStrategyConfiguration>
            <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
            <ns1:initialBid>
              <ns1:maxCpc>120</ns1:maxCpc>
            </ns1:initialBid>
          </ns1:biddingStrategyConfiguration>
          <ns1:settings xsi:type="ns1:TargetingSetting">
            <ns1:criterionType>TARGET_LIST</ns1:criterionType>
            <ns1:targetAll>ACTIVE</ns1:targetAll>
          </ns1:settings>
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
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupService</ns1:service>
      <ns1:remainingQuota>49903</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.7685</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000001</ns1:campaignId>
            <ns1:campaignTrackId>1111111111</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000001</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222221</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>ACTIVE</ns1:targetAll>
            </ns1:settings>
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
          </ns1:adGroup>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループを更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 | 

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
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:campaignId>2000000001</ns1:campaignId>
          <ns1:adGroupId>3000000001</ns1:adGroupId>
          <ns1:adGroupName>sample adgroup</ns1:adGroupName>
          <ns1:userStatus>ACTIVE</ns1:userStatus>
          <ns1:biddingStrategyConfiguration>
            <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
            <ns1:initialBid>
              <ns1:maxCpc>120</ns1:maxCpc>
            </ns1:initialBid>
          </ns1:biddingStrategyConfiguration>
          <ns1:settings xsi:type="ns1:TargetingSetting">
            <ns1:criterionType>TARGET_LIST</ns1:criterionType>
            <ns1:targetAll>ACTIVE</ns1:targetAll>
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
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupService</ns1:service>
      <ns1:remainingQuota>49875</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.8844</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000001</ns1:campaignId>
            <ns1:campaignTrackId>1111111111</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000001</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222221</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>ACTIVE</ns1:targetAll>
            </ns1:settings>
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
          </ns1:adGroup>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告グループを削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
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
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:accountId>1000000001</ns1:accountId>
          <ns1:campaignId>1000000001</ns1:campaignId>
          <ns1:adGroupId>1000000001</ns1:adGroupId>
        </ns1:operand>
        <ns1:operand>
          <ns1:accountId>1000000001</ns1:accountId>
          <ns1:campaignId>1000000001</ns1:campaignId>
          <ns1:adGroupId>1000000002</ns1:adGroupId>
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
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupService</ns1:service>
      <ns1:remainingQuota>49875</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.8844</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroup>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>2000000001</ns1:campaignId>
            <ns1:campaignTrackId>1111111111</ns1:campaignTrackId>
            <ns1:campaignName>sample campaign</ns1:campaignName>
            <ns1:adGroupId>3000000001</ns1:adGroupId>
            <ns1:adGroupTrackId>2222222221</ns1:adGroupTrackId>
            <ns1:adGroupName>sample adgroup</ns1:adGroupName>
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
            <ns1:settings xsi:type="ns1:TargetingSetting">
              <ns1:criterionType>TARGET_LIST</ns1:criterionType>
              <ns1:targetAll>ACTIVE</ns1:targetAll>
            </ns1:settings>
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
          </ns1:adGroup>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
