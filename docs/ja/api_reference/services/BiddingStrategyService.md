# BiddingStrategyService
BiddingStrategyServiceでは、自動入札設定の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/BiddingStrategyService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/BiddingStrategyService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201909/BiddingStrategy
#### サービス概要
自動入札設定の取得および追加・更新・削除を行います。
#### 操作
BiddingStrategyServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[BiddingStrategy](../data/BiddingStrategy)

## get
自動入札設定に関する情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [BiddingStrategySelector](../data/BiddingStrategy/BiddingStrategySelector.md) | 自動入札設定を取得します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>1234567890</accountId>
        <biddingStrategyIds>20001</biddingStrategyIds>
        <biddingStrategyIds>20002</biddingStrategyIds>
        <biddingStrategyIds>20003</biddingStrategyIds>
        <biddingStrategyIds>20004</biddingStrategyIds>
        <biddingStrategyIds>20005</biddingStrategyIds>
        <biddingStrategyTypes>TARGET_CPA</biddingStrategyTypes>
        <biddingStrategyTypes>TARGET_SPEND</biddingStrategyTypes>
        <biddingStrategyTypes>TARGET_ROAS</biddingStrategyTypes>
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

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [BiddingStrategyPage](../data/BiddingStrategy/BiddingStrategyPage.md) | 取得される広告グループのエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1567167410059</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/BiddingStrategy">
      <ns2:rval>
        <totalNumEntries>3</totalNumEntries>
        <Page.Type>BiddingStrategyPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>99999999</ns2:targetCpa>
              <ns2:bidCeiling>500</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>1</ns2:bidCeiling>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>1000.0</ns2:targetRoas>
              <ns2:bidCeiling>5000</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
自動入札設定を追加します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [BiddingStrategyOperation](../data/BiddingStrategy/BiddingStrategyOperation.md) | 自動入札設定を作成します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <biddingStrategyName>TargetCpaBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetCpaBiddingScheme">
            <biddingStrategyType>TARGET_CPA</biddingStrategyType>
            <targetCpa>99999999</targetCpa>
            <bidCeiling>500</bidCeiling>
            <bidFloor>1</bidFloor>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyName>TargetSpendBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetSpendBiddingScheme">
            <biddingStrategyType>TARGET_SPEND</biddingStrategyType>
            <bidCeiling>1</bidCeiling>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyName>TargetRoasBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetRoasBiddingScheme">
            <biddingStrategyType>TARGET_ROAS</biddingStrategyType>
            <targetRoas>1000.0</targetRoas>
            <bidCeiling>5000</bidCeiling>
            <bidFloor>10</bidFloor>
          </biddingScheme>
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
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategy/BiddingStrategyReturnValue.md) | 操作結果を含む自動入札設定に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1567167410100</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/BiddingStrategy">
      <ns2:rval>
        <ListReturnValue.Type>BiddingStrategyReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>99999999</ns2:targetCpa>
              <ns2:bidCeiling>500</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>1</ns2:bidCeiling>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>1000.0</ns2:targetRoas>
              <ns2:bidCeiling>5000</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
自動入札設定を更新します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [BiddingStrategyOperation](../data/BiddingStrategy/BiddingStrategyOperation.md) | 自動入設定を更新します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <biddingStrategyId>20003</biddingStrategyId>
          <biddingStrategyName>set TargetCpaBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetCpaBiddingScheme">
            <biddingStrategyType>TARGET_CPA</biddingStrategyType>
            <targetCpa>11111111</targetCpa>
            <bidCeiling>100</bidCeiling>
            <bidFloor>10</bidFloor>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyId>20004</biddingStrategyId>
          <biddingStrategyName>set TargetSpendBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetSpendBiddingScheme">
            <biddingStrategyType>TARGET_SPEND</biddingStrategyType>
            <bidCeiling>2</bidCeiling>
          </biddingScheme>
        </operand>
        <operand>
          <biddingStrategyId>20005</biddingStrategyId>
          <biddingStrategyName>set TargetRoasBiddingScheme</biddingStrategyName>
          <biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetRoasBiddingScheme">
            <biddingStrategyType>TARGET_ROAS</biddingStrategyType>
            <targetRoas>100.0</targetRoas>
            <bidCeiling>3000</bidCeiling>
            <bidFloor>1</bidFloor>
          </biddingScheme>
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
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategy/BiddingStrategyReturnValue.md) | 操作結果を含む自動入札設定に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1567167410128</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/BiddingStrategy">
      <ns2:rval>
        <ListReturnValue.Type>BiddingStrategyReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>set TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>11111111</ns2:targetCpa>
              <ns2:bidCeiling>100</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>set TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>2</ns2:bidCeiling>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>set TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>100.0</ns2:targetRoas>
              <ns2:bidCeiling>3000</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
自動入札設定を削除します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [BiddingStrategyOperation](../data/BiddingStrategy/BiddingStrategyOperation.md) | 自動入札設定を削除します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <biddingStrategyId>20001</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20002</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20003</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20004</biddingStrategyId>
        </operand>
        <operand>
          <biddingStrategyId>20005</biddingStrategyId>
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
| rval | [BiddingStrategyReturnValue](../data/BiddingStrategy/BiddingStrategyReturnValue.md) | 操作結果を含む自動入札設定に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/BiddingStrategy" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>BiddingStrategy</ns2:service>
      <ns2:requestTime>1567167410154</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/BiddingStrategy">
      <ns2:rval>
        <ListReturnValue.Type>BiddingStrategyReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20003</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetCpaBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetCpaBiddingScheme">
              <ns2:biddingStrategyType>TARGET_CPA</ns2:biddingStrategyType>
              <ns2:targetCpa>11111111</ns2:targetCpa>
              <ns2:bidCeiling>100</ns2:bidCeiling>
              <ns2:bidFloor>10</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20004</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetSpendBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetSpendBiddingScheme">
              <ns2:biddingStrategyType>TARGET_SPEND</ns2:biddingStrategyType>
              <ns2:bidCeiling>2</ns2:bidCeiling>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:biddingStrategy>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:biddingStrategyId>20005</ns2:biddingStrategyId>
            <ns2:biddingStrategyName>TargetRoasBiddingScheme</ns2:biddingStrategyName>
            <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
            <ns2:biddingScheme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetRoasBiddingScheme">
              <ns2:biddingStrategyType>TARGET_ROAS</ns2:biddingStrategyType>
              <ns2:targetRoas>100.0</ns2:targetRoas>
              <ns2:bidCeiling>3000</ns2:bidCeiling>
              <ns2:bidFloor>1</ns2:bidFloor>
            </ns2:biddingScheme>
          </ns2:biddingStrategy>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
