# AdGroupService
AdGroupServiceでは、広告グループに関する情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/AdGroupService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/AdGroupService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201805/AdGroup

#### サービス概要
広告グループに関する情報の取得および追加・更新・削除を行います。

#### 操作
AdGroupServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)


#### オブジェクト
[AdGroup](../data/AdGroup)

## get
広告グループに関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AdGroupSelector](../data/AdGroup/AdGroupSelector.md) | 操作の対象とする広告グループです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
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
        <userStatuses>ACTIVE</userStatuses>
        <userStatuses>PAUSED</userStatuses>
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
| rval | [AdGroupPage](../data/AdGroup/AdGroupPage.md) | 取得される広告グループのエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1523506327746</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroup">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupTrackId>0</ns2:adGroupTrackId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:criterionType>TARGET_LIST</ns2:criterionType>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:urlReviewData>
              <ns2:urlApprovalStatus>APPROVED</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
            <ns2:adGroupAdRotationMode>
              <ns2:adRotationMode>OPTIMIZE</ns2:adRotationMode>
            </ns2:adGroupAdRotationMode>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
広告グループを追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroup/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AdGroup">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupName>test adGroup.</adGroupName>
          <userStatus>ACTIVE</userStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <criterionType>TARGET_LIST</criterionType>
            <targetAll>ACTIVE</targetAll>
          </settings>
          <trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</trackingUrl>
          <customParameters>
            <parameters>
              <key>site</key>
              <value>yahoo</value>
            </parameters>
            <parameters>
              <key>id1</key>
              <value>1234</value>
            </parameters>
            <parameters>
              <key>id2</key>
              <value>a7h59A98yu</value>
            </parameters>
          </customParameters>
          <adGroupAdRotationMode>
            <adRotationMode>ROTATE_FOREVER</adRotationMode>
          </adGroupAdRotationMode>
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
| rval | [AdGroupReturnValue](../data/AdGroup/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1523506327789</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroup">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupTrackId>0</ns2:adGroupTrackId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:criterionType>TARGET_LIST</ns2:criterionType>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:urlReviewData>
              <ns2:inReviewUrl>
                <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
                <ns2:parameters>
                  <ns2:key>site</ns2:key>
                  <ns2:value>yahoo</ns2:value>
                </ns2:parameters>
                <ns2:parameters>
                  <ns2:key>id1</ns2:key>
                  <ns2:value>1234</ns2:value>
                </ns2:parameters>
                <ns2:parameters>
                  <ns2:key>id2</ns2:key>
                  <ns2:value>a7h59A98yu</ns2:value>
                </ns2:parameters>
              </ns2:inReviewUrl>
              <ns2:urlApprovalStatus>REVIEW</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
            <ns2:adGroupAdRotationMode>
              <ns2:adRotationMode>ROTATE_FOREVER</ns2:adRotationMode>
            </ns2:adGroupAdRotationMode>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループを更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroup/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AdGroup">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <adGroupName>set test adGroup.</adGroupName>
          <userStatus>PAUSED</userStatus>
          <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
            <criterionType>TARGET_LIST</criterionType>
            <targetAll>DEACTIVE</targetAll>
          </settings>
          <adGroupAdRotationMode>
            <adRotationMode>OPTIMIZE</adRotationMode>
          </adGroupAdRotationMode>
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
| rval | [AdGroupReturnValue](../data/AdGroup/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1523506327836</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroup">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupTrackId>0</ns2:adGroupTrackId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:criterionType>TARGET_LIST</ns2:criterionType>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:urlReviewData>
              <ns2:urlApprovalStatus>APPROVED</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
            <ns2:adGroupAdRotationMode>
              <ns2:adRotationMode>OPTIMIZE</ns2:adRotationMode>
            </ns2:adGroupAdRotationMode>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告グループを削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroup/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AdGroup">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
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
| rval | [AdGroupReturnValue](../data/AdGroup/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroup" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroup</ns2:service>
      <ns2:requestTime>1523506327884</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroup">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroup>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:campaignTrackId>100000001</ns2:campaignTrackId>
            <ns2:campaignName>test campaign.</ns2:campaignName>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:adGroupTrackId>0</ns2:adGroupTrackId>
            <ns2:adGroupName>test adGroup.</ns2:adGroupName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TargetingSetting">
              <ns2:criterionType>TARGET_LIST</ns2:criterionType>
              <ns2:targetAll>ACTIVE</ns2:targetAll>
            </ns2:settings>
            <ns2:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</ns2:trackingUrl>
            <ns2:customParameters>
              <ns2:parameters>
                <ns2:key>site</ns2:key>
                <ns2:value>yahoo</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id1</ns2:key>
                <ns2:value>1234</ns2:value>
              </ns2:parameters>
              <ns2:parameters>
                <ns2:key>id2</ns2:key>
                <ns2:value>a7h59A98yu</ns2:value>
              </ns2:parameters>
            </ns2:customParameters>
            <ns2:urlReviewData>
              <ns2:urlApprovalStatus>APPROVED</ns2:urlApprovalStatus>
            </ns2:urlReviewData>
            <ns2:adGroupAdRotationMode>
              <ns2:adRotationMode>OPTIMIZE</ns2:adRotationMode>
            </ns2:adGroupAdRotationMode>
          </ns2:adGroup>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
