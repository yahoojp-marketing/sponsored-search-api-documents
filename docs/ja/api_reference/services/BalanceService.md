# BalanceService
BalanceServiceでは、選択したアカウントのアカウント残高の情報を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/BalanceService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/BalanceService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201909/Balance
#### サービス概要
アカウントの残高の情報を取得するWebサービスです。取得したアカウント残高の情報は入札戦略などに活用できます。
#### 操作
BalanceServiceで提供される操作を説明します。

+ [get](#get)

#### オブジェクト
[Balance](../data/Balance)

## get
選択したアカウント残高に関する情報を取得します。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [BalanceSelector](../data/Balance/BalanceSelector.md) | 操作の対象とするアカウントです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/Balance" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/Balance" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountIds>1111</accountIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [BalancePage](../data/Balance/BalancePage.md) | 取得されるアカウント残高に関するエントリーを表します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/Balance" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>Balance</ns2:service>
      <ns2:requestTime>1547792971147</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/Balance">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:balance>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:balance>10000</ns2:balance>
          </ns2:balance>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
