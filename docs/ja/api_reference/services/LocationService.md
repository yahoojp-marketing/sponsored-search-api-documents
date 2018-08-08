# LocationService
LocationServiceでは、アカウントのロケーション情報を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/LocationService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/LocationService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201808/Location
#### サービス概要
アカウントのコロケーションの取得を行います。<br>
※LocationService自体は、LocationServiceのWSDLに記載されたメインURLを使用します。

##### LocationServiceの場合
メインURLを使用してLocationServiceに対してリクエストを送信します。<br>
メインURLはLocationServiceのWSDLに含まれています。

##### その他のWebサービスの場合
ローカルURLを使用してリクエストを送信します。ローカルURLを作成するには、<br> LocationServiceを使用して、アカウントに割り当てられたコロケーションのURL接頭部を入手します。<br>
次に、URL接頭部を現行バージョンおよび特定のサービス名と組み合わせて、ローカルURLを作成します。<br>
<br>
また、ロケーション情報の有効な期間は決まっていませんが、頻繁に変更されるものではありませんので、<br>
各処理の度に取得する必要はなく、無効になった時点で取得しなおすようにしてください。

#### 操作
LocationServiceで提供される操作を説明します。

+ [get](#get)

#### オブジェクト
[LocationService](../data/Location)

## get
アカウントに割り当てられたロケーションのURL接頭部の情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 |
＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
  xmlns:ns1="http://ss.yahooapis.jp/V201808/Location">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

＜リクエストサンプル＞（代行認証）
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/Location" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/Location">
      <accountId>1234567890</accountId>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [LocationReturnValue](../data/Location/LocationReturnValue.md) | 操作結果を含むロケーション情報のコンテナです。 |

＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/Location" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>Location</ns2:service>
      <ns2:requestTime>1522028288536</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/Location">
      <ns2:rval>
        <operationSucceeded>true</operationSucceeded>
        <ns2:value>https://ss.yahooapis.jp/xxx</ns2:value>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
