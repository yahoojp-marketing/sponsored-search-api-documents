# CampaignTargetService
CampaignTargetServiceでは、キャンペーンのターゲティング設定に関する情報の取得および更新を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/CampaignTargetService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/CampaignTargetService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201901/CampaignTarget

#### サービス概要
キャンペーンのターゲティング設定に関する情報の取得および更新を行います。<br>
※各種ターゲティングは入札調整率（bidmultiplier）のみ変更可能です。<br>
※ターゲティングごとに利用できる操作が異なります。詳しくは下の表をご覧ください。<br>
※ネットワークターゲティングの場合はmutate(SET)ができません。<br>
　変更する場合は一旦mutate(REMOVE)を行い、その後mutate(ADD)を行う必要があります。

| ターゲット | mutate(ADD) | mutate(SET) | mutate(REMOVE) | 備考 |
|---|---|---|---|---|
| 曜日・時間帯ターゲティング | OK | OK | OK | |
| 地域ターゲティング | OK | OK | OK | |
| デバイスターゲティング | NG | OK | NG | 新規登録および削除は実施できません。<br>キャンペーン新規作成時に自動で登録されるデバイスターゲティング<br>(bidMultiplierは"1"に設定)の変更のみ可能です。 |
| ネットワークターゲティング | OK | NG | OK | bidmultiplierの登録はできません。 |

#### 操作
CampaignTargetServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[CampaignTarget](../data/CampaignTarget)

## get
キャンペーンのターゲティング設定に関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [CampaignTargetSelector](../data/CampaignTarget/CampaignTargetSelector.md) | 操作の対象とするキャンペーンのターゲティング設定です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>10001</campaignIds>
        <campaignIds>10002</campaignIds>
        <campaignIds>10003</campaignIds>
        <campaignIds>10004</campaignIds>
        <campaignIds>10005</campaignIds>
        <targetIds>20001</targetIds>
        <targetIds>20002</targetIds>
        <targetIds>20003</targetIds>
        <targetIds>20004</targetIds>
        <targetIds>20005</targetIds>
        <targetIds>JP-01-0010</targetIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>1000</ns2:numberResults>
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
| rval | [CampaignTargetPage](../data/CampaignTarget/CampaignTargetPage.md) | 取得されるキャンペーンのターゲティング設定に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1547792971626</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignTarget">
      <ns2:rval>
        <totalNumEntries>6</totalNumEntries>
        <Page.Type>CampaignTargetPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NetworkTarget">
              <ns2:targetId>20002</ns2:targetId>
              <ns2:targetType>NETWORK</ns2:targetType>
              <ns2:networkCoverageType>YAHOO_SEARCH</ns2:networkCoverageType>
            </ns2:target>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlatformTarget">
              <ns2:targetId>20003</ns2:targetId>
              <ns2:targetType>PLATFORM</ns2:targetType>
              <ns2:platformType>SMART_PHONE</ns2:platformType>
            </ns2:target>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlatformTarget">
              <ns2:targetId>20004</ns2:targetId>
              <ns2:targetType>PLATFORM</ns2:targetType>
              <ns2:platformType>TABLET</ns2:platformType>
            </ns2:target>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlatformTarget">
              <ns2:targetId>20005</ns2:targetId>
              <ns2:targetType>PLATFORM</ns2:targetType>
              <ns2:platformType>DESKTOP</ns2:platformType>
            </ns2:target>
            <ns2:bidMultiplier>1.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
キャンペーンのターゲティング設定に関する情報を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignTargetOperation](../data/CampaignTarget/CampaignTargetOperation.md) | 操作の対象となるキャンペーンのターゲティング設定および操作の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleTarget">
            <targetType>SCHEDULE</targetType>
            <dayOfWeek>FRIDAY</dayOfWeek>
            <startHour>10</startHour>
            <startMinute>ZERO</startMinute>
            <endHour>19</endHour>
            <endMinute>ZERO</endMinute>
          </target>
          <bidMultiplier>5.0</bidMultiplier>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
            <excludedType>INCLUDED</excludedType>
          </target>
          <bidMultiplier>5.0</bidMultiplier>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="NetworkTarget">
            <targetType>NETWORK</targetType>
            <networkCoverageType>YAHOO_SEARCH</networkCoverageType>
          </target>
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
| rval | [CampaignTargetReturnValue](../data/CampaignTarget/CampaignTargetReturnValue.md) | 操作結果を含むキャンペーンのターゲット設定に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1547792971662</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignTarget">
      <ns2:rval>
        <ListReturnValue.Type>CampaignTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NetworkTarget">
              <ns2:targetId>20002</ns2:targetId>
              <ns2:targetType>NETWORK</ns2:targetType>
              <ns2:networkCoverageType>YAHOO_SEARCH</ns2:networkCoverageType>
            </ns2:target>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)

キャンペーンのターゲティング設定に関する情報を変更します。<br>
※入札調整率（bidmultiplier）のみ変更可能です。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignTargetOperation](../data/CampaignTarget/CampaignTargetOperation.md) | 操作の対象とするキャンペーンのターゲティング設定です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleTarget">
            <targetId>20001</targetId>
            <targetType>SCHEDULE</targetType>
          </target>
          <bidMultiplier>10.0</bidMultiplier>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
          </target>
          <bidMultiplier>10.0</bidMultiplier>
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
| rval | [CampaignTargetReturnValue](../data/CampaignTarget/CampaignTargetReturnValue.md) | 取得されるキャンペーンのターゲティング設定に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1547792971726</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignTarget">
      <ns2:rval>
        <ListReturnValue.Type>CampaignTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>10.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
キャンペーンのターゲティング設定に関する情報を削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [CampaignTargetOperation](../data/CampaignTarget/CampaignTargetOperation.md) | 操作の対象とするキャンペーンのターゲティング設定です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ScheduleTarget">
            <targetId>20001</targetId>
            <targetType>SCHEDULE</targetType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
          </target>
        </operand>
        <operand>
          <campaignId>10001</campaignId>
          <target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="LocationTarget">
            <targetId>JP-01-0010</targetId>
            <targetType>LOCATION</targetType>
          </target>
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
| rval | [CampaignTargetReturnValue](../data/CampaignTarget/CampaignTargetReturnValue.md) | 取得されるキャンペーンのターゲティング設定に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/CampaignTarget" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>CampaignTarget</ns2:service>
      <ns2:requestTime>1547792971761</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/CampaignTarget">
      <ns2:rval>
        <ListReturnValue.Type>CampaignTargetReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ScheduleTarget">
              <ns2:targetId>20001</ns2:targetId>
              <ns2:targetType>SCHEDULE</ns2:targetType>
              <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
              <ns2:startHour>10</ns2:startHour>
              <ns2:startMinute>ZERO</ns2:startMinute>
              <ns2:endHour>19</ns2:endHour>
              <ns2:endMinute>ZERO</ns2:endMinute>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:LocationTarget">
              <ns2:targetId>JP-01-0010</ns2:targetId>
              <ns2:targetType>LOCATION</ns2:targetType>
              <ns2:provinceNameJA>北海道</ns2:provinceNameJA>
              <ns2:provinceNameEN>Hokkaido</ns2:provinceNameEN>
              <ns2:cityNameJA>伊達市</ns2:cityNameJA>
              <ns2:cityNameEN>Date</ns2:cityNameEN>
              <ns2:excludedType>INCLUDED</ns2:excludedType>
              <ns2:targetingStatus>ACTIVE</ns2:targetingStatus>
            </ns2:target>
            <ns2:bidMultiplier>5.0</ns2:bidMultiplier>
          </ns2:campaignTarget>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignTarget>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:NetworkTarget">
              <ns2:targetId>20002</ns2:targetId>
              <ns2:targetType>NETWORK</ns2:targetType>
              <ns2:networkCoverageType>YAHOO_SEARCH</ns2:networkCoverageType>
            </ns2:target>
          </ns2:campaignTarget>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
