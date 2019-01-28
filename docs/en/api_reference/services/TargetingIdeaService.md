# TargetingIdeaService
TargetingIdeaService is a service that suggests new related keywords based on the specified value.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/TargetingIdeaService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/TargetingIdeaService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201901/TargetingIdea

#### Overview
Suggests related keywords based on the specified information.

#### Operation
Explains the operations provided by TargetingIdeaService.

+ [get](#get)

#### Object
[TargetingIdea](../data/TargetingIdea)

## get

### Request
Acquires related keyword information.

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [TargetingIdeaSelector](../data/TargetingIdea/TargetingIdeaSelector.md) | Specify conditions related keyword suggestions. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/TargetingIdea" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/TargetingIdea" xmlns:ns2="http://ss.yahooapis.jp/V201901">
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

### Response
Response Fields

| Parameter | Data Type | Description |
|---|---|---|
| rval | [TargetingIdeaPage](../data/TargetingIdea/TargetingIdeaPage.md) | The entry related to auquired suggestion. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/TargetingIdea" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>TargetingIdea</ns2:service>
      <ns2:requestTime>1547793755750</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/TargetingIdea">
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
