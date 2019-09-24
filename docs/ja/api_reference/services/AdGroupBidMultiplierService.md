# AdGroupBidMultiplierService
AdGroupBidMultiplierServiceでは、広告グループに関する入札価格調整率の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/AdGroupBidMultiplierService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/AdGroupBidMultiplierService?wsdl |
#### Namespace
http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier
#### サービス概要
広告グループに関する入札価格調整率の取得および設定、更新、削除を行います。
#### 操作
AdGroupBidMultiplierServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)


#### オブジェクト
[AdGroupBidMultiplier](../data/AdGroupBidMultiplier)

## get
広告グループに関する入札価格調整率を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AdGroupBidMultiplierSelector](../data/AdGroupBidMultiplier/AdGroupBidMultiplierSelector.md) | 操作の対象とする広告グループの入札価格調整率です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <adGroupIds>20001</adGroupIds>
        <adGroupIds>20002</adGroupIds>
        <adGroupIds>20003</adGroupIds>
        <adGroupIds>20004</adGroupIds>
        <adGroupIds>20005</adGroupIds>
        <platformTypes>DESKTOP</platformTypes>
        <platformTypes>TABLET</platformTypes>
        <platformTypes>SMART_PHONE</platformTypes>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>100</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupBidMultiplierPage](../data/AdGroupBidMultiplier/AdGroupBidMultiplierPage.md) | 取得される広告グループの入札価格調整率のエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>AdGroupBidMultiplier</ns2:service>
      <ns2:requestTime>1547793791751</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupBidMultiplierPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupBidMultiplier>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:platformType>DESKTOP</ns2:platformType>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:adGroupBidMultiplier>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループに関する入札価格調整率を設定、更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupBidMultiplierOperation](../data/AdGroupBidMultiplier/AdGroupBidMultiplierOperation.md) | 操作の対象となる広告グループの入札価格調整率と処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <platformType>DESKTOP</platformType>
          <bidMultiplier>10.0</bidMultiplier>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupBidMultiplierReturnValue](../data/AdGroupBidMultiplier/AdGroupBidMultiplierReturnValue.md) | 操作結果を含む広告グループの入札価格調整率に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>AdGroupBidMultiplier</ns2:service>
      <ns2:requestTime>1547793791762</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupBidMultiplierReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupBidMultiplier>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:platformType>DESKTOP</ns2:platformType>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:adGroupBidMultiplier>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告グループに設定済みの入札価格調整率を削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupBidMultiplierOperation](../data/AdGroupBidMultiplier/AdGroupBidMultiplierOperation.md) | 操作の対象となる広告グループの入札価格調整率と処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <platformType>DESKTOP</platformType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupBidMultiplierReturnValue](../data/AdGroupBidMultiplier/AdGroupBidMultiplierReturnValue.md) | 操作結果を含む広告グループの入札価格調整率に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>AdGroupBidMultiplier</ns2:service>
      <ns2:requestTime>1547793791772</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/AdGroupBidMultiplier">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupBidMultiplierReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupBidMultiplier>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:platformType>DESKTOP</ns2:platformType>
          </ns2:adGroupBidMultiplier>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
