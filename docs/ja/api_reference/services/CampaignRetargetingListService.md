# CampaignRetargetingListService
CampaignRetargetingListServiceでは、キャンペーン階層におけるターゲットリストの設定（設定情報の取得、追加、更新、削除）を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/CampaignRetargetingListService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/CampaignRetargetingListService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V201901/CampaignRetargetingList

#### サービス概要
キャンペーン階層におけるターゲットリストの設定（設定情報の取得、追加、更新、削除）を行います。

#### 操作
CampaignRetargetingListServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[CampaignRetargetingList](../data/CampaignRetargetingList)

## get
キャンペーン階層におけるターゲットリストの設定情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [CampaignRetargetingListSelector](../data/CampaignRetargetingList/CampaignRetargetingListSelector.md) | getメソッドの検索条件（実行パラメータ）を保持します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <selector>
        <accountId>1111</accountId>
        <campaignIds>1</campaignIds>
        <campaignIds>2</campaignIds>
        <targetListIds>100000001</targetListIds>
        <targetListIds>100000002</targetListIds>
        <excludedType>INCLUDED</excludedType>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignRetargetingListPage](../data/CampaignRetargetingList/CampaignRetargetingListPage.md) | getメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignRetargetingList</ns2:service>
      <ns2:requestTime>1547793561624</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignRetargetingList">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignRetargetingList>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:campaignId>1</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionTargetList>
              <ns2:targetListId>100000001</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:campaignRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
キャンペーン階層におけるターゲットリストの設定情報を追加します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignRetargetingListOperation](../data/CampaignRetargetingList/CampaignRetargetingListOperation.md) | mutateメソッドで操作対象となるターゲットリストと処理内容を保持します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList">
      <operations>
        <operator>ADD</operator>
        <accountId>1111111</accountId>
        <operand>
          <campaignId>22222</campaignId>
          <criterionTargetList>
            <targetListId>3333</targetListId>
          </criterionTargetList>
          <excludedType>INCLUDED</excludedType>
          <bidMultiplier>1.5</bidMultiplier>
        </operand>
        <operand>
          <campaignId>3333</campaignId>
          <criterionTargetList>
            <targetListId>4444</targetListId>
          </criterionTargetList>
          <excludedType>EXCLUDED</excludedType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignRetargetingListReturnValue](../data/CampaignRetargetingList/CampaignRetargetingListReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignRetargetingList</ns2:service>
      <ns2:requestTime>1547793561639</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignRetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>CampaignRetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionTargetList>
              <ns2:targetListId>3333</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.5</ns2:bidMultiplier>
          </ns2:campaignRetargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionTargetList>
              <ns2:targetListId>4444</ns2:targetListId>
              <ns2:targetListName>test2</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>EXCLUDED</ns2:excludedType>
          </ns2:campaignRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
キャンペーン階層におけるターゲットリストの設定情報を更新します。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignRetargetingListOperation](../data/CampaignRetargetingList/CampaignRetargetingListOperation.md) | mutateメソッドで操作対象となるターゲットリストと処理内容を保持します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList">
      <operations>
        <operator>SET</operator>
        <accountId>1111111</accountId>
        <operand>
          <campaignId>22222</campaignId>
          <criterionTargetList>
            <targetListId>3333</targetListId>
          </criterionTargetList>
          <excludedType>INCLUDED</excludedType>
          <bidMultiplier>1.5</bidMultiplier>
        </operand>
        <operand>
          <campaignId>3333</campaignId>
          <criterionTargetList>
            <targetListId>4444</targetListId>
          </criterionTargetList>
          <excludedType>EXCLUDED</excludedType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignRetargetingListReturnValue](../data/CampaignRetargetingList/CampaignRetargetingListReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignRetargetingList</ns2:service>
      <ns2:requestTime>1547793561712</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignRetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>CampaignRetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionTargetList>
              <ns2:targetListId>3333</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.5</ns2:bidMultiplier>
          </ns2:campaignRetargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionTargetList>
              <ns2:targetListId>4444</ns2:targetListId>
              <ns2:targetListName>test2</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>EXCLUDED</ns2:excludedType>
          </ns2:campaignRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
キャンペーン階層におけるターゲットリストの設定情報を削除します。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignRetargetingListOperation](../data/CampaignRetargetingList/CampaignRetargetingListOperation.md) | mutateメソッドで操作対象となるターゲットリストと処理内容を保持します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1111111</accountId>
        <operand>
          <campaignId>22222</campaignId>
          <criterionTargetList>
            <targetListId>3333</targetListId>
          </criterionTargetList>
          <excludedType>INCLUDED</excludedType>
        </operand>
        <operand>
          <campaignId>3333</campaignId>
          <criterionTargetList>
            <targetListId>4444</targetListId>
          </criterionTargetList>
          <excludedType>EXCLUDED</excludedType>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [CampaignRetargetingListReturnValue](../data/CampaignRetargetingList/CampaignRetargetingListReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignRetargetingList" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignRetargetingList</ns2:service>
      <ns2:requestTime>1547793561731</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignRetargetingList">
      <ns2:rval>
        <ListReturnValue.Type>CampaignRetargetingListReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionTargetList>
              <ns2:targetListId>3333</ns2:targetListId>
              <ns2:targetListName>test1</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:bidMultiplier>1.5</ns2:bidMultiplier>
          </ns2:campaignRetargetingList>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignRetargetingList>
            <ns2:accountId>1111111</ns2:accountId>
            <ns2:campaignId>22222</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:criterionTargetList>
              <ns2:targetListId>4444</ns2:targetListId>
              <ns2:targetListName>test2</ns2:targetListName>
              <ns2:retargetingTrackId>0</ns2:retargetingTrackId>
            </ns2:criterionTargetList>
            <ns2:excludedType>EXCLUDED</ns2:excludedType>
          </ns2:campaignRetargetingList>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
