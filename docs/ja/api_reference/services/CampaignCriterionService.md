# CampaignCriterionService
CampaignCriterionServiceでは、キャンペーンの除外クライテリアの取得および追加・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/CampaignCriterionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/CampaignCriterionService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201909/CampaignCriterion
#### サービス概要
キャンペーンの除外クライテリアの取得および追加・削除を行います。
#### 操作
CampaignCriterionServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[CampaignCriterion](../data/CampaignCriterion)

## get

#### リクエスト
キャンペーンの除外クライテリアに関する情報を取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [CampaignCriterionSelector](../data/CampaignCriterion/CampaignCriterionSelector.md) | 操作の対象とするキャンペーンのクライテリアです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <criterionIds>20001</criterionIds>
        <criterionIds>20002</criterionIds>
        <criterionIds>20003</criterionIds>
        <criterionIds>20004</criterionIds>
        <criterionIds>20005</criterionIds>
        <criterionUse>NEGATIVE</criterionUse>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>100</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignCriterionPage](../data/CampaignCriterion/CampaignCriterionPage.md) | 取得されるキャンペーンのクライテリアのエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignCriterion</ns2:service>
      <ns2:requestTime>1547793146733</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignCriterion">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>CampaignCriterionPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NegativeCampaignCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionUse>NEGATIVE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>20001</ns2:criterionId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
          </ns2:campaignCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

#### リクエスト
キャンペーンの除外クライテリアを追加します。

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operation | ○ | [CampaignCriterionOperation](../data/CampaignCriterion/CampaignCriterionOperation.md) | 操作の対象となるキャンペーンのクライテリアと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="NegativeCampaignCriterion">
          <campaignId>10001</campaignId>
          <criterionUse>NEGATIVE</criterionUse>
          <criterion xsi:type="Keyword">
            <type>KEYWORD</type>
            <text>test keyword.</text>
            <matchType>PHRASE</matchType>
          </criterion>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignCriterionReturnValue](../data/CampaignCriterion/CampaignCriterionReturnValue.md) | 操作結果を含むキャンペーンのクライテリアに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignCriterion</ns2:service>
      <ns2:requestTime>1547793146756</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignCriterion">
      <ns2:rval>
        <ListReturnValue.Type>CampaignCriterionReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NegativeCampaignCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionUse>NEGATIVE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>20001</ns2:criterionId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
          </ns2:campaignCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

#### リクエスト
キャンペーンの除外クライテリアを削除します。

| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operation | ○ | [CampaignCriterionOperation](../data/CampaignCriterion/CampaignCriterionOperation.md) | 操作の対象となるキャンペーンのクライテリアと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="NegativeCampaignCriterion">
          <campaignId>10001</campaignId>
          <criterionUse>NEGATIVE</criterionUse>
          <criterion xsi:type="Keyword">
            <criterionId>20001</criterionId>
            <type>KEYWORD</type>
          </criterion>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignCriterionReturnValue](../data/CampaignCriterion/CampaignCriterionReturnValue.md) | 操作結果を含むキャンペーンのクライテリアに関する情報のコンテナです。 |
##### ＜レスポンストサンプル＞

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignCriterion" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignCriterion</ns2:service>
      <ns2:requestTime>1547793146784</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignCriterion">
      <ns2:rval>
        <ListReturnValue.Type>CampaignCriterionReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignCriterion xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NegativeCampaignCriterion">
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionUse>NEGATIVE</ns2:criterionUse>
            <ns2:criterion xsi:type="ns2:Keyword">
              <ns2:criterionId>20001</ns2:criterionId>
              <ns2:type>KEYWORD</ns2:type>
              <ns2:text>test keyword.</ns2:text>
              <ns2:matchType>PHRASE</ns2:matchType>
            </ns2:criterion>
          </ns2:campaignCriterion>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
