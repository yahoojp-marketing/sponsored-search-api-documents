# CampaignFeedService
CampaignFeedServiceでは、キャンペーンのFeedItem情報の取得および更新を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/CampaignFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/CampaignFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/CampaignFeed
#### サービス概要
キャンペーンのFeedItem情報の取得およびFeedItem情報の追加・更新・削除を行います。
#### 操作
CampaignFeedServiceで提供される操作を説明します。
+ [get](#get)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[CampaignFeed](../data/CampaignFeed)

## get
キャンペーンのFeedItem情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [CampaignFeedSelector](../data/CampaignFeed/CampaignFeedSelector.md) | 操作の対象とするFeedItem情報です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <feedItemIds>20001</feedItemIds>
        <feedItemIds>20002</feedItemIds>
        <feedItemIds>20003</feedItemIds>
        <feedItemIds>20004</feedItemIds>
        <feedItemIds>20005</feedItemIds>
        <placeholderTypes>QUICKLINK</placeholderTypes>
        <placeholderTypes>CALLEXTENSION</placeholderTypes>
        <placeholderTypes>CALLOUT</placeholderTypes>
        <placeholderTypes>STRUCTURED_SNIPPET</placeholderTypes>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>100</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignFeedPage](../data/CampaignFeed/CampaignFeedPage.md) | 取得されるキャンペーンのFeedItem情報のエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>CampaignFeed</ns2:service>
      <ns2:requestTime>1523506332070</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/CampaignFeed">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>CampaignFeedPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:campaignFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:feedItemId>20001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:campaignFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:campaignFeedList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
キャンペーンにFeedItem情報を追加・更新・解除（削除）します。
* FeedItem情報を解除するときは空の情報で更新します。
* 1つのキャンペーンに設定できるFeedItem情報は、QUICKLINKS、CALLEXTENSIONでそれぞれ20件までです。
* CALLEXTENSIONについて1キャンペーンあたり1件の設定をお薦めします。
* 1リクエスト内で同一のcampaignIdに複数のFeedItem情報は設定できません。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignFeedOperation](../data/CampaignFeed/CampaignFeedOperation.md) | 操作の対象とするキャンペーンのFeedItem情報および操作の内容を表します。<br> FeedItem情報は上書きされます。<br>FeedItem情報の設定を解除するときは空のデータで更新してください。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/CampaignFeed">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <placeholderType>QUICKLINK</placeholderType>
          <campaignFeed>
            <feedItemId>20001</feedItemId>
          </campaignFeed>
          <devicePlatform>DESKTOP</devicePlatform>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignFeedReturnValue](../data/CampaignFeed/CampaignFeedReturnValue.md) | 操作結果を含むキャンペーンのFeedItem情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/CampaignFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>CampaignFeed</ns2:service>
      <ns2:requestTime>1523506332086</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/CampaignFeed">
      <ns2:rval>
        <ListReturnValue.Type>CampaignFeedReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:campaignFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:feedItemId>20001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:campaignFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:campaignFeedList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
