# LocationService
LocationServiceでは、アカウントのロケーション情報を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V6.0/LocationService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V6.0/LocationService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
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
  xmlns:ns1="http://ss.yahooapis.jp/V6">
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
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
  xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [LocationReturnValue](../data/LocationReturnValue.md) | 操作結果を含むロケーション情報のコンテナです。 | 

＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>LocationService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:value>https://ss.yahooapis.jp/～</ns1:value>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
