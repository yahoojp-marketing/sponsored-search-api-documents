# TargetingIdeaService
TargetingIdeaServiceは、指定された情報を元に新しいキーワード候補を提案するサービスです。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/TargetingIdeaService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/TargetingIdeaService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201909/TargetingIdea

#### サービス概要
指定された情報を元に新しいキーワード候補を提案するサービスです。

#### 操作
TargetingIdeaServiceで提供される操作を説明します。

+ [get](#get)

#### オブジェクト
[TargetingIdea](../data/TargetingIdea)

## get
関連するキーワード情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [TargetingIdeaSelector](../data/TargetingIdea/TargetingIdeaSelector.md) | 関連キーワードを提案する条件を指定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/TargetingIdea" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/TargetingIdea" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>12345</accountId>
        <searchParameter xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelatedToKeywordSearchParameter">
          <searchParameterUse>RELATED_TO_KEYWORD</searchParameterUse>
          <keywords>
            <type>KEYWORD</type>
            <text>スポーツ</text>
            <matchType>PHRASE</matchType>
          </keywords>
          <keywords>
            <type>KEYWORD</type>
            <text>夏</text>
            <matchType>PHRASE</matchType>
          </keywords>
        </searchParameter>
        <searchParameter xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelatedToUrlSearchParameter">
          <searchParameterUse>RELATED_TO_URL</searchParameterUse>
          <url>http://www.yahoo.co.jp/</url>
        </searchParameter>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [TargetingIdeaPage](../data/TargetingIdea/TargetingIdeaPage.md) | 取得される提案に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/TargetingIdea" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>TargetingIdea</ns2:service>
      <ns2:requestTime>1547793755727</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/TargetingIdea">
      <ns2:rval>
        <totalNumEntries>3</totalNumEntries>
        <Page.Type>TargetingIdeaPage</Page.Type>
        <ns2:values>
          <ns2:accountId>12345</ns2:accountId>
          <ns2:data>
            <ns2:key>KEYWORD</ns2:key>
            <ns2:value xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:KeywordAttribute">
              <ns2:attributeType>KEYWORD</ns2:attributeType>
              <ns2:value>
                <ns2:type>KEYWORD</ns2:type>
                <ns2:text>dummy keyword 0001</ns2:text>
                <ns2:matchType>EXACT</ns2:matchType>
              </ns2:value>
            </ns2:value>
          </ns2:data>
        </ns2:values>
        <ns2:values>
          <ns2:accountId>12345</ns2:accountId>
          <ns2:data>
            <ns2:key>KEYWORD</ns2:key>
            <ns2:value xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:KeywordAttribute">
              <ns2:attributeType>KEYWORD</ns2:attributeType>
              <ns2:value>
                <ns2:type>KEYWORD</ns2:type>
                <ns2:text>dummy keyword 0001</ns2:text>
                <ns2:matchType>PHRASE</ns2:matchType>
              </ns2:value>
            </ns2:value>
          </ns2:data>
        </ns2:values>
        <ns2:values>
          <ns2:accountId>12345</ns2:accountId>
          <ns2:data>
            <ns2:key>KEYWORD</ns2:key>
            <ns2:value xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:KeywordAttribute">
              <ns2:attributeType>KEYWORD</ns2:attributeType>
              <ns2:value>
                <ns2:type>KEYWORD</ns2:type>
                <ns2:text>dummy keyword 0001</ns2:text>
                <ns2:matchType>BROAD</ns2:matchType>
              </ns2:value>
            </ns2:value>
          </ns2:data>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
