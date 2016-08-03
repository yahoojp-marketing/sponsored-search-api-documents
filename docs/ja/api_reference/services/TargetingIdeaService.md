# TargetingIdeaService
TargetingIdeaServiceは、指定された情報を元に新しいキーワード候補を提案するサービスです。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/TargetingIdeaService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/TargetingIdeaService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
指定された情報を元に新しいキーワード候補を提案するサービスです。

#### 操作
TargetingIdeaServiceで提供される操作を説明します。

## get
関連するキーワード情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [TargetingIdeaSelector](../data/TargetingIdeaSelector.md) | 関連キーワードを提案する条件を指定します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:searchParameter xsi:type="ns1:RelatedToKeywordSearchParameter">
          <ns1:searchParameterUse>RELATED_TO_KEYWORD</ns1:searchParameterUse>
          <ns1:keywords>
            <ns1:type>KEYWORD</ns1:type>
            <ns1:text>スポーツ</ns1:text>
            <ns1:matchType>PHRASE</ns1:matchType>
          </ns1:keywords>
          <ns1:keywords>
            <ns1:type>KEYWORD</ns1:type>
            <ns1:text>夏</ns1:text>
            <ns1:matchType>PHRASE</ns1:matchType>
          </ns1:keywords>
        </ns1:searchParameter>
        <ns1:searchParameter xsi:type="ns1:RelatedToUrlSearchParameter">
          <ns1:searchParameterUse>RELATED_TO_URL</ns1:searchParameterUse>
          <ns1:url>http://www.yahoo.co.jp/</ns1:url>
          <ns1:includeSubUrls>FALSE</ns1:includeSubUrls>
        </ns1:searchParameter>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [TargetingIdeaPage](../data/TargetingIdeaPage.md) | 取得される提案に関するエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>TargetingIdeaService</ns1:service>
      <ns1:remainingQuota>119950</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.2758</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>3</ns1:totalNumEntries>
        <ns1:Page.Type>TargetingIdeaPage</ns1:Page.Type>
        <ns1:values>
          <ns1:data>
            <ns1:key>KEYWORD</ns1:key>
            <ns1:value xsi:type="ns1:KeywordAttribute">
              <ns1:attributeType>KEYWORD</ns1:attributeType>
              <ns1:value>
                <ns1:type>KEYWORD</ns1:type>
                <ns1:text>dummy keyword 0001</ns1:text>
                <ns1:matchType>EXACT</ns1:matchType>
              </ns1:value>
            </ns1:value>
          </ns1:data>
        </ns1:values>
        <ns1:values>
          <ns1:data>
            <ns1:key>KEYWORD</ns1:key>
            <ns1:value xsi:type="ns1:KeywordAttribute">
              <ns1:attributeType>KEYWORD</ns1:attributeType>
              <ns1:value>
                <ns1:type>KEYWORD</ns1:type>
                <ns1:text>dummy keyword 0001</ns1:text>
                <ns1:matchType>PHRASE</ns1:matchType>
              </ns1:value>
            </ns1:value>
          </ns1:data>
        </ns1:values>
        <ns1:values>
          <ns1:data>
            <ns1:key>KEYWORD</ns1:key>
            <ns1:value xsi:type="ns1:KeywordAttribute">
              <ns1:attributeType>KEYWORD</ns1:attributeType>
              <ns1:value>
                <ns1:type>KEYWORD</ns1:type>
                <ns1:text>dummy keyword 0001</ns1:text>
                <ns1:matchType>BROAD</ns1:matchType>
              </ns1:value>
            </ns1:value>
          </ns1:data>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
