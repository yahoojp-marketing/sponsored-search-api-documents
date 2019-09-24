# FeedFolderService
FeedFolderServiceでは、自動データ挿入のリスト情報の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/FeedFolderService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/FeedFolderService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201909/FeedFolder
#### サービス概要
自動データ挿入のリスト情報の取得および追加・更新・削除を行います。
#### 操作
FeedFoldersServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[FeedFolder](../data/FeedFolder)

## get
自動データ挿入のリスト情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [FeedFolderSelector](../data/FeedFolder/FeedFolderSelector.md) | 操作の対象とする自動データ挿入のリスト情報です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>1234567890</accountId>
        <feedFolderIds>10001</feedFolderIds>
        <feedFolderIds>10002</feedFolderIds>
        <feedFolderIds>10003</feedFolderIds>
        <feedFolderIds>10004</feedFolderIds>
        <feedFolderIds>10005</feedFolderIds>
        <placeholderTypes>AD_CUSTOMIZER</placeholderTypes>
        <placeholderTypes>DYNAMIC_AD_FOR_SEARCH_PAGE_FEEDS</placeholderTypes>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>1000</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [FeedFolderPage](../data/FeedFolder/FeedFolderPage.md) | 取得される自動データ挿入のリスト情報に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1547793097039</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedFolder">
      <ns2:rval>
        <totalNumEntries>2</totalNumEntries>
        <Page.Type>FeedFolderPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10002</ns2:feedFolderId>
            <ns2:feedFolderName>test dynamic ad for search page feed.</ns2:feedFolderName>
            <ns2:placeholderType>DYNAMIC_AD_FOR_SEARCH_PAGE_FEEDS</ns2:placeholderType>
            <ns2:domain>https://www.yahoo.co.jp</ns2:domain>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
FeedItem情報を追加します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedFolderOperation](../data/FeedFolder/FeedFolderOperation.md) | 操作の対象とする自動データ挿入のリスト情報と処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedFolder">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <feedFolderName>test feedFolder.</feedFolderName>
          <feedAttribute>
            <feedAttributeName>integerFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_INTEGER</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>priceFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_PRICE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>dateFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_DATE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>stringFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_STRING</placeholderField>
          </feedAttribute>
        </operand>
        <operand>
          <accountId>0</accountId>
          <feedFolderName>test dsa feed.</feedFolderName>
          <placeholderType>DYNAMIC_AD_FOR_SEARCH_PAGE_FEEDS</placeholderType>
          <domain>https://www.yahoo.co.jp</domain>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolder/FeedFolderReturnValue.md) | 操作結果を含むFeedItem情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1547793097059</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedFolder">
      <ns2:rval>
        <ListReturnValue.Type>FeedFolderReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10002</ns2:feedFolderId>
            <ns2:feedFolderName>test dynamic ad for search page feed.</ns2:feedFolderName>
            <ns2:placeholderType>DYNAMIC_AD_FOR_SEARCH_PAGE_FEEDS</ns2:placeholderType>
            <ns2:domain>https://www.yahoo.co.jp</ns2:domain>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
FeedItem情報を更新します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedFolderOperation](../data/FeedFolder/FeedFolderOperation.md) | 操作の対象とする自動データ挿入のリスト情報と処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedFolder">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <feedFolderId>10001</feedFolderId>
          <feedAttribute>
            <feedAttributeName>integerFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_INTEGER</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>priceFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_PRICE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>dateFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_DATE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>stringFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_STRING</placeholderField>
          </feedAttribute>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolder/FeedFolderReturnValue.md) | 操作結果を含む自動データ挿入のリスト情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1547793097079</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedFolder">
      <ns2:rval>
        <ListReturnValue.Type>FeedFolderReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>5</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>6</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>7</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>8</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
FeedItem情報を削除します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedFolderOperation](../data/FeedFolder/FeedFolderOperation.md) | 操作の対象とするFeedItem情報です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/FeedFolder">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <feedFolderId>10001</feedFolderId>
        </operand>
        <operand>
          <accountId>0</accountId>
          <feedFolderId>10002</feedFolderId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolder/FeedFolderReturnValue.md) | 操作結果を含む自動データ挿入のリスト情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1547793097092</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/FeedFolder">
      <ns2:rval>
        <ListReturnValue.Type>FeedFolderReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>5</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>6</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>7</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>8</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10002</ns2:feedFolderId>
            <ns2:feedFolderName>test dynamic ad for search page feed.</ns2:feedFolderName>
            <ns2:placeholderType>DYNAMIC_AD_FOR_SEARCH_PAGE_FEEDS</ns2:placeholderType>
            <ns2:domain>https://www.yahoo.co.jp</ns2:domain>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
