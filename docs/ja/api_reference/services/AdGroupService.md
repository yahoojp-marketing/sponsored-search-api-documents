# AdGroupService
AdGroupServiceでは、広告グループに関する情報の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/AdGroupService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/AdGroupService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
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
                <ns1:userStatuses>ACTIVE</ns1:userStatuses>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:biddingStrategyIds>xxxxxxxx</ns1:biddingStrategyIds>
                <ns1:biddingStrategyIds>xxxxxxxx</ns1:biddingStrategyIds>
                <ns1:biddingStrategyIds>xxxxxxxx</ns1:biddingStrategyIds>
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
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>xxxxxxxx</ns1:biddingStrategyId>
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
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
##### ＜レスポンスサンプル＞（入札戦略の登録失敗）
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
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 2</ns1:adGroupName>
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
                  <ns1:biddingStrategyFailedReason>BIDDING_STRATEGY_CANNOT_BE_OVERRIDDEN</ns1:biddingStrategyFailedReason>
                  <ns1:failedBiddingStrategyConfiguration>
                     <ns1:biddingStrategyId>xxxxxxxx</ns1:biddingStrategyId>
                     <ns1:biddingStrategyName>Sample bidding EnhancedCpcBidding</ns1:biddingStrategyName>
                     <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     <ns1:biddingStrategySource>ADGROUP</ns1:biddingStrategySource>
                     <ns1:biddingScheme xsi:type="ns1:EnhancedCpcBiddingScheme">
                        <ns1:biddingStrategyType>ENHANCED_CPC</ns1:biddingStrategyType>
                     </ns1:biddingScheme>
                  </ns1:failedBiddingStrategyConfiguration>
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
               <!--ManualCPC-->
               <ns1:operand>
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                     <ns1:initialBid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                     </ns1:initialBid>
                  </ns1:biddingStrategyConfiguration>
               </ns1:operand>
               <!--EnhancedCpcBidding-->
               <ns1:operand>
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>xxxxxxxx</ns1:biddingStrategyId>
                     <ns1:initialBid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                     </ns1:initialBid>
                  </ns1:biddingStrategyConfiguration>
               </ns1:operand>
               <!--No BiddingStrategy-->
               <ns1:operand>
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:initialBid>
                        <ns1:maxCpc>120</ns1:maxCpc>
                     </ns1:initialBid>
                  </ns1:biddingStrategyConfiguration>
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
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroup>
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>xxxxxxxx</ns1:biddingStrategyId>
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
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <!--ManualCPCへ変更-->
                <ns1:operand>
                    <ns1:accountId>xxxxxxxx</ns1:accountId>
                    <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                    <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                    <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:biddingStrategyConfiguration>
                       <ns1:biddingStrategyType>MANUAL_CPC</ns1:biddingStrategyType>
                       <ns1:initialBid>
                          <ns1:maxCpc>120</ns1:maxCpc>
                       </ns1:initialBid>
                    </ns1:biddingStrategyConfiguration>
                </ns1:operand>
                <!--EnhancedCpcBiddingへ変更-->
                <ns1:operand>
                    <ns1:accountId>xxxxxxxx</ns1:accountId>
                    <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                    <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                    <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:biddingStrategyConfiguration>
                       <ns1:biddingStrategyId>xxxxxxxx</ns1:biddingStrategyId>
                    </ns1:biddingStrategyConfiguration>
                </ns1:operand>
                <!--設定した入札戦略を取消す-->
                <ns1:operand>
                    <ns1:accountId>xxxxxxxx</ns1:accountId>
                    <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                    <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                    <ns1:adGroupName>ad group name 3</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:biddingStrategyConfiguration>
                       <ns1:biddingStrategyType>NONE</ns1:biddingStrategyType>
                    </ns1:biddingStrategyConfiguration>
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
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroup>
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>xxxxxxxx</ns1:biddingStrategyId>
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
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
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
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>xxxxxxxx</ns1:accountId>
                    <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                    <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>xxxxxxxx</ns1:accountId>
                    <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                    <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroup>
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
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
                  <ns1:accountId>xxxxxxxx</ns1:accountId>
                  <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                  <ns1:campaignName>campaign name</ns1:campaignName>
                  <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                  <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                  <ns1:userStatus>ACTIVE</ns1:userStatus>
                  <ns1:biddingStrategyConfiguration>
                     <ns1:biddingStrategyId>xxxxxxxx</ns1:biddingStrategyId>
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
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
