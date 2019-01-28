# AccountService
AccountServiceでは、アカウントに関する情報の取得および更新を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/AccountService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/AccountService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V201901/Account

#### サービス概要
アカウント情報の取得および更新を行います。

#### 操作
AccountServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[Account](../data/Account)

## get
アカウントに関する情報を取得します。契約状況などのフィルタ条件を設定することが可能です。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AccountSelector](../data/Account/AccountSelector.md) | 操作の対象とするアカウントに関する情報を表します。<br>空の場合は、アクセスが可能なすべてのアカウントが返されます。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/Account" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/Account" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <selector>
        <accountIds>1111</accountIds>
        <accountIds>2222</accountIds>
        <accountTypes>PREPAY</accountTypes>
        <accountTypes>INVOICE</accountTypes>
        <accountStatuses>INPROGRESS</accountStatuses>
        <accountStatuses>WAIT_DECIDE</accountStatuses>
        <accountStatuses>SUSPENDED</accountStatuses>
        <accountStatuses>SERVING</accountStatuses>
        <accountStatuses>ENDED</accountStatuses>
        <accountStatuses>CANCELED</accountStatuses>
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
| rval | [AccountPage](../data/Account/AccountPage.md) | 取得されるアカウントに関するエントリーを表します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/Account" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>Account</ns2:service>
      <ns2:requestTime>1547793059096</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/Account">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:account>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:accountName>SampleAccount_UpdatedOn_20190118</ns2:accountName>
            <ns2:accountType>INVOICE</ns2:accountType>
            <ns2:accountStatus>SERVING</ns2:accountStatus>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:budget>
              <ns2:amount>5000</ns2:amount>
              <ns2:limitChargeType>MONTHLY</ns2:limitChargeType>
              <ns2:startDate>20120529</ns2:startDate>
              <ns2:endDate>20371231</ns2:endDate>
            </ns2:budget>
            <ns2:autoTaggingEnabled>FALSE</ns2:autoTaggingEnabled>
          </ns2:account>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
アカウントに関する情報を更新します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [AccountOperation](../data/Account/AccountOperation.md) | 操作の対象とするアカウント情報と処理の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/Account" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/Account">
      <operations>
        <operator>SET</operator>
        <operand>
          <accountId>1111</accountId>
          <accountName>SampleAccount_UpdatedOn_20190118</accountName>
          <deliveryStatus>ACTIVE</deliveryStatus>
          <autoTaggingEnabled>FALSE</autoTaggingEnabled>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AccountReturnValue](../data/Account/AccountReturnValue.md) | 操作結果を含むアカウント情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/Account" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>Account</ns2:service>
      <ns2:requestTime>1547793059166</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/Account">
      <ns2:rval>
        <ListReturnValue.Type>AccountReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:account>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:accountName>SampleAccount_UpdatedOn_20190118</ns2:accountName>
            <ns2:accountType>INVOICE</ns2:accountType>
            <ns2:accountStatus>SERVING</ns2:accountStatus>
            <ns2:deliveryStatus>ACTIVE</ns2:deliveryStatus>
            <ns2:budget>
              <ns2:amount>5000</ns2:amount>
              <ns2:limitChargeType>MONTHLY</ns2:limitChargeType>
              <ns2:startDate>20120529</ns2:startDate>
              <ns2:endDate>20371231</ns2:endDate>
            </ns2:budget>
            <ns2:autoTaggingEnabled>FALSE</ns2:autoTaggingEnabled>
          </ns2:account>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
