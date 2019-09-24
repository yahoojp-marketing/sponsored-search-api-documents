# CampaignSharedSetService
CampaignSharedSetServiceでは、対象外キーワードリストのキャンペーンへの関連付け設定などを行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/CampaignSharedSetService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/CampaignSharedSetService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201909/CampaignSharedSet

#### サービス概要
対象外キーワードリストのキャンペーンへの関連付け設定などを行います。

#### 操作
CampaignSharedSetServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[CampaignSharedSet](../data/CampaignSharedSet)

## get
キャンペーンと対象外キーワードリストの関連付け情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [CampaignSharedSetSelector](../data/CampaignSharedSet/CampaignSharedSetSelector.md) | getメソッドの検索条件（実行パラメータ）を保持するオブジェクトです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>111111</accountId>
        <campaignIds>44</campaignIds>
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
| rval | [CampaignSharedSetPage](../data/CampaignSharedSet/CampaignSharedSetPage.md) | getメソッドの実行結果（全Entityのリスト）を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignSharedSet</ns2:service>
      <ns2:requestTime>1547793435051</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignSharedSet">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignSharedSet>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>11</ns2:sharedListId>
            <ns2:campaignId>44</ns2:campaignId>
            <ns2:sharedListName>sample</ns2:sharedListName>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
          </ns2:campaignSharedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
キャンペーンに対象外キーワードリストの関連付け設定を行います。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignSharedSetOperation](../data/CampaignSharedSet/CampaignSharedSetOperation.md) | mutateメソッドで操作対象となるキャンペーンと<br>対象外キーワードリストの関連付け情報を保持するオブジェクトです。|

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet">
      <operations>
        <operator>ADD</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>11</sharedListId>
          <campaignId>44</campaignId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignSharedSetReturnValue](../data/CampaignSharedSet/CampaignSharedSetReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignSharedSet</ns2:service>
      <ns2:requestTime>1547793435084</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignSharedSet">
      <ns2:rval>
        <ListReturnValue.Type>CampaignSharedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignSharedSet>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:campaignId>44</ns2:campaignId>
            <ns2:sharedListName>sample</ns2:sharedListName>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
          </ns2:campaignSharedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
キャンペーンと対象外キーワードリストの関連付け設定を削除します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignSharedSetOperation](../data/CampaignSharedSet/CampaignSharedSetOperation.md) | mutateメソッドで操作対象となるキャンペーンと<br>対象外キーワードリストの関連付け情報を保持するオブジェクトです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>2222</sharedListId>
          <campaignId>3333</campaignId>
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
| rval | [CampaignSharedSetReturnValue](../data/CampaignSharedSet/CampaignSharedSetReturnValue.md) |mutateメソッドの実行結果（全Entityのリスト）を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignSharedSet</ns2:service>
      <ns2:requestTime>1547793435115</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignSharedSet">
      <ns2:rval>
        <ListReturnValue.Type>CampaignSharedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignSharedSet>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:campaignId>44</ns2:campaignId>
            <ns2:sharedListName>sample</ns2:sharedListName>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
          </ns2:campaignSharedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
