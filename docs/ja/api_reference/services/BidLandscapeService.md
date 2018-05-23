# BidLandscapeService
BidLandscapeServiceは、入札単価を変更したときのインプレッションやクリックの変化を予測します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/BidLandscapeService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/BidLandscapeService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/BidLandscape
#### サービス概要
入札単価を変更したときのインプレッションやクリックの変化を予測します。
#### 操作
BidLandscapeServiceで提供される操作を説明します。

+ [get](#get)

#### オブジェクト
[BidLandscape](../data/BidLandscape)

## get
入札単価を変更したときのインプレッションやクリックの変化を予測します。<br>
一度に指定できるクライテリアは最大100個です。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [BidLandscapeSelector](../data/BidLandscape/BidLandscapeSelector.md) | 操作の対象とするアカウント、キャンペーン、広告グループ、クライテリアを指定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/BidLandscape" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/BidLandscape">
      <selector>
        <accountId>1</accountId>
        <campaignId>1000000001</campaignId>
        <adGroupId>1000000001</adGroupId>
        <criterionIds>447</criterionIds>
        <criterionIds>448</criterionIds>
        <criterionIds>449</criterionIds>
        <criterionIds>450</criterionIds>
        <simType>ADGROUP</simType>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [BidLandscapePage](../data/BidLandscape/BidLandscapePage.md) | 取得される予測値に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/BidLandscape" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>BidLandscape</ns2:service>
      <ns2:requestTime>1523506330869</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/BidLandscape">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>BidLandscapePage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:data xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdGroupBidLandscape">
            <ns2:campaignId>1</ns2:campaignId>
            <ns2:adGroupId>1</ns2:adGroupId>
            <ns2:landscapePoints>
              <ns2:bid>100</ns2:bid>
              <ns2:clicks>400</ns2:clicks>
              <ns2:cost>200</ns2:cost>
              <ns2:marginalCpc>300</ns2:marginalCpc>
              <ns2:impressions>500</ns2:impressions>
            </ns2:landscapePoints>
            <ns2:BidLandscape.Type>AdGroupBidLandscape</ns2:BidLandscape.Type>
            <ns2:type>DEFAULT</ns2:type>
            <ns2:landscapeCurrent>true</ns2:landscapeCurrent>
          </ns2:data>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
