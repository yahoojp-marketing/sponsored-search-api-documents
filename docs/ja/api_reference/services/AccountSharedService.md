# AccountSharedService
AccountSharedServiceは、アカウント内で共有できる対象外キーワードリストの照会、追加、変更、削除を行ないます。


#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/AccountSharedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/AccountSharedService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201805/AccountShared

#### サービス概要
対象外キーワードリストの照会、追加、変更、削除を行ないます。
対象外キーワードリストは1アカウントあたり20件まで追加できます。
なお代行認証の場合は、Soapヘッダーで指定したaccountIdのみ照会、操作が可能です。

#### 操作
AccountSharedServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)


#### オブジェクト
[AccountShared](../data/AccountShared)

## get
対象外キーワードリストの情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AccountSharedSelector](../data/AccountShared/AccountSharedSelector.md) | getメソッドの検索条件（実行パラメータ）を保持するオブジェクトです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>111111</accountId>
        <sharedListIds>22</sharedListIds>
        <sharedListIds>33</sharedListIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AccountSharedPage](../data/AccountShared/AccountSharedPage.md) | getメソッドの実行結果（全エンティティのリスト）を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506326966</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_UpdatedOn_20180412</ns2:name>
            <ns2:memberCount>1</ns2:memberCount>
            <ns2:referenceCount>1</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
アカウントに対象外キーワードリストを追加します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountShared/AccountSharedOperation.md) | mutateメソッドで操作対象となるキャンペーンを保持するオブジェクトです。|

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AccountShared">
      <operations>
        <operator>ADD</operator>
        <accountId>1111</accountId>
        <operand>
          <name>sample</name>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
mutateメソッドの実行結果（全エンティティのリスト）を保持します。

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountShared/AccountSharedReturnValue.md)| mutateメソッドの実行結果（全エンティティのリスト）を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506327013</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <ListReturnValue.Type>AccountSharedReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_CreatedOn_20180412</ns2:name>
            <ns2:referenceCount>0</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
対象外キーワードリストの設定を変更します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountShared/AccountSharedOperation.md)|  mutateメソッドで操作対象となるキャンペーンを保持するオブジェクトです。|

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AccountShared">
      <operations>
        <operator>SET</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>2222</sharedListId>
          <name>SampleSharedAccount_UpdatedOn_20180412</name>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
mutateメソッドの実行結果（全エンティティのリスト）を保持します。

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountShared/AccountSharedReturnValue.md) | mutateメソッドの実行結果（全エンティティのリスト）を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506327037</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <ListReturnValue.Type>AccountSharedReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:sharedListId>2222</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_UpdatedOn_20180412</ns2:name>
            <ns2:memberCount>1</ns2:memberCount>
            <ns2:referenceCount>1</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
アカウントから対象外キーワードリストを削除します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AccountSharedOperation](../data/AccountShared/AccountSharedOperation.md) |  mutateメソッドで操作対象となるキャンペーンを保持するオブジェクトです。|

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AccountShared">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>2222</sharedListId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
mutateメソッドの実行結果（全エンティティのリスト）を保持します。

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AccountSharedReturnValue](../data/AccountShared/AccountSharedReturnValue.md) |mutateメソッドの実行結果（全エンティティのリスト）を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AccountShared" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AccountShared</ns2:service>
      <ns2:requestTime>1523506327056</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AccountShared">
      <ns2:rval>
        <ListReturnValue.Type>AccountSharedReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountShared>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:sharedListId>2222</ns2:sharedListId>
            <ns2:name>SampleSharedAccount_UpdatedOn_20180412</ns2:name>
            <ns2:memberCount>1</ns2:memberCount>
            <ns2:referenceCount>1</ns2:referenceCount>
          </ns2:accountShared>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
