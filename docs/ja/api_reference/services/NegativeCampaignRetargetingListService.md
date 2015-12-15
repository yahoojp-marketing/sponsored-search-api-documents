# NegativeCampaignRetargetingListService
NegativeCampaignRetargetingListServiceでは、キャンペーンレベルでのターゲットリスト除外対象設定に関する情報の取得および追加・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V6.0/NegativeCampaignRetargetingListService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V6.0/NegativeCampaignRetargetingListService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
キャンペーンレベルでのターゲットリスト除外対象設定に関する情報の取得および追加・削除を行います。

#### 操作
NegativeCampaignRetargetingListServiceで提供される操作を説明します。

## get
キャンペーンレベルでのターゲットリスト除外対象設定に関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [NegativeCampaignRetargetingListSelector](../data/NegativeCampaignRetargetingListSelector.md) | 操作の対象とするキャンペーンレベルでのターゲットリスト除外対象設定です。 | 

##### ＜リクエストサンプル＞
```xml
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
        <ns1:campaignIds>100000002</ns1:campaignIds>
        <ns1:campaignIds>100000003</ns1:campaignIds>
        <ns1:campaignIds>100000004</ns1:campaignIds>
        <ns1:targetListIds>100000005</ns1:targetListIds>
        <ns1:targetListIds>100000006</ns1:targetListIds>
        <ns1:targetListIds>100000007</ns1:targetListIds>
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
| rval | [NegativeCampaignRetargetingListPage](../data/NegativeCampaignRetargetingListPage.md) | 取得されるキャンペーンレベルでのターゲットリスト除外対象設定のエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>NegativeCampaignRetargetingListService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>3</ns1:totalNumEntries>
        <ns1:Page.Type>NegativeCampaignRetargetingListPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:negativeCampaignRetargetingList>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>1000000002</ns1:campaignId>
            <ns1:campaignName>campaign name</ns1:campaignName>
            <ns1:criterionTargetList>
              <ns1:targetListId>1000000003</ns1:targetListId>
              <ns1:targetListName>targetList name</ns1:targetListName>
            </ns1:criterionTargetList>
          </ns1:negativeCampaignRetargetingList>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
キャンペーンレベルでのターゲットリスト除外対象設定を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [NegativeCampaignRetargetingListOperation](../data/NegativeCampaignRetargetingListOperation.md) | キャンペーンレベルでのターゲットリスト除外対象設定と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
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
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:operand>
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000003</ns1:targetListId>
          </ns1:criterionTargetList>
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
| rval | [NegativeCampaignRetargetingListReturnValue](../data/NegativeCampaignRetargetingListReturnValue.md) | キャンペーンレベルでのターゲットリスト除外対象設定に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>NegativeCampaignRetargetingListService</ns1:service>
      <ns1:remainingQuota>1972</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.9414</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>NegativeCampaignRetargetingListReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:negativeCampaignRetargetingList>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>1000000002</ns1:campaignId>
            <ns1:campaignName>campaign name</ns1:campaignName>
            <ns1:criterionTargetList>
              <ns1:targetListId>1000000003</ns1:targetListId>
              <ns1:targetListName>targetList name</ns1:targetListName>
            </ns1:criterionTargetList>
          </ns1:negativeCampaignRetargetingList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
キャンペーンレベルでのターゲットリスト除外対象設定を削除します。

#### リクエスト

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [NegativeCampaignRetargetingListOperation](../data/NegativeCampaignRetargetingListOperation.md) | キャンペーンレベルでのターゲットリスト除外対象設定と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
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
        <ns1:operator>REMOVE</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:operand>
          <ns1:accountId>100000001</ns1:accountId>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000003</ns1:targetListId>
          </ns1:criterionTargetList>
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
| rval | [NegativeCampaignRetargetingListReturnValue](../data/NegativeCampaignRetargetingListReturnValue.md) | キャンペーンレベルでのターゲットリスト除外対象設定に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>NegativeCampaignRetargetingListService</ns1:service>
      <ns1:remainingQuota>1972</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.9414</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>NegativeCampaignRetargetingListReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:negativeCampaignRetargetingList>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignId>1000000002</ns1:campaignId>
            <ns1:campaignName>campaign name</ns1:campaignName>
            <ns1:criterionTargetList>
              <ns1:targetListId>1000000003</ns1:targetListId>
              <ns1:targetListName>targetList name</ns1:targetListName>
            </ns1:criterionTargetList>
          </ns1:negativeCampaignRetargetingList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
