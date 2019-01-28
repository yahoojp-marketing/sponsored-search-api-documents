# AccountTrackingUrlService
AccountTrackingUrlServiceでは、アカウントトラッキングに関する情報の取得および更新を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/AccountTrackingUrlService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/AccountTrackingUrlService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201901/AccountTrackingUrl

#### サービス概要
アカウントトラッキングに関する情報の取得および更新を行います。

#### 操作
AccountTrackingUrlServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[AccountTrackingUrl](../data/AccountTrackingUrl)

## get
アカウントトラッキングに関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AccountTrackingUrlSelector](../data/AccountTrackingUrl/AccountTrackingUrlSelector.md) | 操作の対象とするアカウントトラッキングです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AccountTrackingUrl" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/AccountTrackingUrl" xmlns:ns2="http://ss.yahooapis.jp/V201901">
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
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AccountTrackingUrlPage](../data/AccountTrackingUrl/AccountTrackingUrlPage.md) | 取得されるアカウントトラッキングのエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AccountTrackingUrl" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AccountTrackingUrl</ns2:service>
      <ns2:requestTime>1547793699487</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AccountTrackingUrl">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountTrackingUrl>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:accountName>SampleAccount_CreatedOn_20190118</ns2:accountName>
            <ns2:trackingUrl>http://www.xxxxx.com/?url={lpurl}&amp;amp;pid={_id1}</ns2:trackingUrl>
            <ns2:inReviewUrl>http://www.xxxxx2.com/?url={lpurl}&amp;amp;pid={_id1}</ns2:inReviewUrl>
            <ns2:disapprovalReviewUrl>http://www.xxxxx3.com/?url={lpurl}&amp;amp;pid={_id1}</ns2:disapprovalReviewUrl>
            <ns2:urlApprovalStatus>APPROVED</ns2:urlApprovalStatus>
            <ns2:disapprovalReasonCodes>1001</ns2:disapprovalReasonCodes>
            <ns2:disapprovalReasonCodes>1002</ns2:disapprovalReasonCodes>
          </ns2:accountTrackingUrl>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
アカウントトラッキングを更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AccountTrackingUrlOperation](../data/AccountTrackingUrl/AccountTrackingUrlOperation.md) | 操作の対象となるアカウントトラッキングと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AccountTrackingUrl" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AccountTrackingUrl">
      <operations>
        <operator>SET</operator>
        <operand>
          <accountId>1111</accountId>
          <accountName>SampleAccount_UpdatedOn_20190118</accountName>
          <trackingUrl>http://www.xxxxx5.com/?url={lpurl}&amp;amp;pid={_id1}</trackingUrl>
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
| rval | [AccountTrackingUrlReturnValue](../data/AccountTrackingUrl/AccountTrackingUrlReturnValue.md) | 操作結果を含むアカウントトラッキングに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AccountTrackingUrl" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AccountTrackingUrl</ns2:service>
      <ns2:requestTime>1547793699502</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AccountTrackingUrl">
      <ns2:rval>
        <ListReturnValue.Type>AccountTrackingUrlReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountTrackingUrl>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:accountName>SampleAccount_UpdatedOn_20190118</ns2:accountName>
            <ns2:trackingUrl>http://www.xxxxx.com/?url={lpurl}&amp;amp;pid={_id1}</ns2:trackingUrl>
            <ns2:inReviewUrl>http://www.xxxxx5.com/?url={lpurl}&amp;amp;pid={_id1}</ns2:inReviewUrl>
            <ns2:disapprovalReviewUrl>http://www.xxxxx3.com/?url={lpurl}&amp;amp;pid={_id1}</ns2:disapprovalReviewUrl>
            <ns2:urlApprovalStatus>REVIEW</ns2:urlApprovalStatus>
            <ns2:disapprovalReasonCodes>1001</ns2:disapprovalReasonCodes>
            <ns2:disapprovalReasonCodes>1002</ns2:disapprovalReasonCodes>
          </ns2:accountTrackingUrl>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
