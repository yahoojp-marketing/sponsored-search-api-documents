# AdGroupWebpageService
AdGroupWebpageServiceでは、広告グループにPageFeedItemの配信/除外設定を行ないます。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/AdGroupWebpageService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/AdGroupWebpageService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201909/AdGroupWebpage
#### サービス概要
広告グループに対して、PageFeedItemの配信/除外設定を行ないます。
+ 広告グループにPageFeedItemを配信、又は、除外として設定します。
+ 広告グループに関連付けしているPageFeedItemを解除します。
+ 広告グループに設定されているPageFeedItemを照会します。
#### 操作
AdGroupWebpageServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[AdGroupWebpage](../data/AdGroupWebpage/AdGroupWebpage.md)

## get
広告グループに設定されているPageFeedItemの配信/除外設定を取得します。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AdGroupWebpageSelector](../data/AdGroupWebpage/AdGroupWebpageSelector.md) | 照会する条件 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>100000001</accountId>
        <campaignIds>1111</campaignIds>
        <campaignIds>2222</campaignIds>
        <campaignIds>3333</campaignIds>
        <adGroupIds>4444</adGroupIds>
        <adGroupIds>5555</adGroupIds>
        <adGroupIds>6666</adGroupIds>
        <targetIds>7777</targetIds>
        <targetIds>8888</targetIds>
        <targetIds>9999</targetIds>
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
| rval | [AdGroupWebpagePage](../data/AdGroupWebpage/AdGroupWebpagePage.md) | 照会する条件に該当するPageFeedItemの配信/除外設定 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1547793539650</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/AdGroupWebpage">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupWebpagePage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
広告グループにPageFeedItemを配信、又は、除外として設定します。
* 1リクエストで異なるキャンペーン配下の広告グループに対してWebページ情報の設定が可能です。
* 1リクエスト内で同一のadGroupIdに同一組み合わせのWebpageParameterを設定できません。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupWebpageOperation](../data/AdGroupWebpage/AdGroupWebpageOperation.md) | 設定対象の広告グループとPageFeedItemの配信/除外設定 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
          <adGroupId>4444</adGroupId>
          <userStatus>ACTIVE</userStatus>
          <excludedType>INCLUDED</excludedType>
          <webpage>
            <parameter>
              <conditions>
                <type>URL</type>
                <argument>yahoo.co.jp</argument>
              </conditions>
              <conditions>
                <type>PAGE_TITLE</type>
                <argument>YahooJapan</argument>
              </conditions>
              <conditions>
                <type>CUSTOM_LABEL</type>
                <argument>sample</argument>
              </conditions>
            </parameter>
          </webpage>
          <bid>
            <maxCpc>100</maxCpc>
          </bid>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupWebpageReturnValue](../data/AdGroupWebpage/AdGroupWebpageReturnValue.md) | 操作結果を含む広告グループに設定されたPageFeedItemの配信/除外設定 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1547793539679</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/AdGroupWebpage">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループにPageFeedItemを配信、又は、除外として設定します。
* 1リクエストで異なるキャンペーン配下の広告グループに対してWebページ情報の設定が可能です。
* 1リクエスト内で同一のadGroupIdに同一組み合わせのWebpageParameterを設定できません。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupWebpageOperation](../data/AdGroupWebpage/AdGroupWebpageOperation.md) | 設定対象の広告グループとPageFeedItemの配信/除外設定 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
          <adGroupId>4444</adGroupId>
          <userStatus>ACTIVE</userStatus>
          <excludedType>INCLUDED</excludedType>
          <webpage>
            <targetId>7777</targetId>
            <parameter>
              <conditions>
                <type>URL</type>
                <argument>yahoo.co.jp</argument>
              </conditions>
              <conditions>
                <type>PAGE_TITLE</type>
                <argument>YahooJapan</argument>
              </conditions>
              <conditions>
                <type>CUSTOM_LABEL</type>
                <argument>sample</argument>
              </conditions>
            </parameter>
          </webpage>
          <bid>
            <maxCpc>100</maxCpc>
          </bid>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupWebpageReturnValue](../data/AdGroupWebpage/AdGroupWebpageReturnValue.md) | 操作結果を含む広告グループに設定されたPageFeedItemの配信/除外設定 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1547793539705</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/AdGroupWebpage">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告グループに関連付けしているPageFeedItemを解除します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupWebpageOperation](../data/AdGroupWebpage/AdGroupWebpageOperation.md) | 解除対象の広告グループとPageFeedItemの配信/除外設定 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
          <adGroupId>4444</adGroupId>
          <webpage>
            <targetId>7777</targetId>
          </webpage>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupWebpageReturnValue](../data/AdGroupWebpage/AdGroupWebpageReturnValue.md) | 操作結果を含む広告グループから解除されたPageFeedItemの配信/除外設定 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1547793539729</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/AdGroupWebpage">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
