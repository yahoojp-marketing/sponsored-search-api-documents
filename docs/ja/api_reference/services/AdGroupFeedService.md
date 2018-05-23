# AdGroupFeedService
AdGroupFeedServiceでは、広告グループに関するFeedItem情報の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/AdGroupFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/AdGroupFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/AdGroupFeed
#### サービス概要
広告グループのFeedItem情報の取得およびFeedItem情報の追加・更新・削除を行います。
#### 操作
AdGroupFeedServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[AdGroupFeed](../data/AdGroupFeed/AdGroupFeed)

## get
広告グループに設定されているFeedItem情報を取得します。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AdGroupFeedSelector](../data/AdGroupFeed/AdGroupFeedSelector.md) | 操作の対象とするFeedItem情報です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
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
        <feedItemIds>30001</feedItemIds>
        <feedItemIds>30002</feedItemIds>
        <feedItemIds>30003</feedItemIds>
        <feedItemIds>30004</feedItemIds>
        <feedItemIds>30005</feedItemIds>
        <placeholderTypes>QUICKLINK</placeholderTypes>
        <placeholderTypes>CALLEXTENSION</placeholderTypes>
        <placeholderTypes>CALLOUT</placeholderTypes>
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
| rval | [AdGroupFeedPage](../data/AdGroupFeed/AdGroupFeedPage.md) | 指定したFeedItem情報を格納するコンテナです。<br>FeedItem情報を設定していない広告グループは取得できません。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroupFeed</ns2:service>
      <ns2:requestTime>1523506329727</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroupFeed">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupFeedPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:adGroupFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:adGroupId>20001</ns2:adGroupId>
              <ns2:feedItemId>30001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:adGroupFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:adGroupFeedList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループにFeedItem情報を追加・更新・解除（削除）します。更新は常に上書きされるため追加分を含めて更新する必要があります。<br>
* FeedItem情報を解除するときは空の情報で更新します。
* 1リクエストで異なるキャンペーン配下の広告グループに対してFeedItem情報の設定が可能です。
* 1つの広告グループに設定できるFeedItem情報は、QUICKLINKS、CALLEXTENSIONでそれぞれ20件までです。
* CALLEXTENSIONについては1広告グループあたり1件の設定をお薦めします。
* 1リクエスト内で同一のadGroupIdに複数のFeedItem情報を設定できません。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupFeedOperation](../data/AdGroupFeed/AdGroupFeedOperation.md) | 操作の対象とする広告グループのFeedItem情報および操作の内容を表します。<br> FeedItem設定は上書きされます。<br>FeedItem設定を解除するときは空のデータで更新してください。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AdGroupFeed">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <placeholderType>QUICKLINK</placeholderType>
          <adGroupFeed>
            <feedItemId>20001</feedItemId>
          </adGroupFeed>
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
| rval | [AdGroupFeedReturnValue](../data/AdGroupFeed/AdGroupFeedReturnValue.md) | 操作結果を含む広告グループに設定されたFeedItem情報に関するコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupFeed" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroupFeed</ns2:service>
      <ns2:requestTime>1523506329744</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroupFeed">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupFeedReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupFeedList>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            <ns2:adGroupFeed>
              <ns2:accountId>1234567890</ns2:accountId>
              <ns2:campaignId>10001</ns2:campaignId>
              <ns2:adGroupId>20001</ns2:adGroupId>
              <ns2:feedItemId>30001</ns2:feedItemId>
              <ns2:placeholderType>QUICKLINK</ns2:placeholderType>
            </ns2:adGroupFeed>
            <ns2:devicePlatform>DESKTOP</ns2:devicePlatform>
          </ns2:adGroupFeedList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
