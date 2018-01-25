# AdGroupService
AdGroupServiceでは、広告グループに関する情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
広告グループに関する情報の取得および追加・更新・削除を行います。

#### 操作
AdGroupServiceで提供される操作を説明します。

## get
広告グループに関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupSelector](../data/AdGroupSelector.md) | 操作の対象とする広告グループです。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V6">
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
          <startIndex>1</startIndex>
          <numberResults>1000</numberResults>
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
| rval | [AdGroupPage](../data/AdGroupPage.md) | 取得される広告グループのエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">AdGroup</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupPage</Page.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <adGroup>
            <accountId>1234567890</accountId>
            <campaignId>10001</campaignId>
            <campaignTrackId>100000001</campaignTrackId>
            <campaignName>test campaign.</campaignName>
            <adGroupId>20001</adGroupId>
            <adGroupTrackId>0</adGroupTrackId>
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
            <urlReviewData>
              <urlApprovalStatus>APPROVED</urlApprovalStatus>
            </urlReviewData>
            <adGroupAdRotationMode>
              <adRotationMode>OPTIMIZE</adRotationMode>
            </adGroupAdRotationMode>
          </adGroup>
        </values>
      </rval>
    </getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
広告グループを追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V6">
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
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">AdGroup</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutateResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <adGroup>
            <accountId>1234567890</accountId>
            <campaignId>10001</campaignId>
            <campaignTrackId>100000001</campaignTrackId>
            <campaignName>test campaign.</campaignName>
            <adGroupId>20001</adGroupId>
            <adGroupTrackId>0</adGroupTrackId>
            <adGroupName>test adGroup.</adGroupName>
            <userStatus>ACTIVE</userStatus>
            <settings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TargetingSetting">
              <criterionType>TARGET_LIST</criterionType>
              <targetAll>ACTIVE</targetAll>
            </settings>
            <urlReviewData>
              <inReviewUrl>
                <trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={_site}&amp;pid={_id1}&amp;vid={_id2}</trackingUrl>
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
              </inReviewUrl>
              <urlApprovalStatus>REVIEW</urlApprovalStatus>
            </urlReviewData>
            <adGroupAdRotationMode>
              <adRotationMode>ROTATE_FOREVER</adRotationMode>
            </adGroupAdRotationMode>
          </adGroup>
        </values>
      </rval>
    </mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループを更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V6">
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
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">AdGroup</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutateResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <adGroup>
            <accountId>1234567890</accountId>
            <campaignId>10001</campaignId>
            <campaignTrackId>100000001</campaignTrackId>
            <campaignName>test campaign.</campaignName>
            <adGroupId>20001</adGroupId>
            <adGroupTrackId>0</adGroupTrackId>
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
            <urlReviewData>
              <urlApprovalStatus>APPROVED</urlApprovalStatus>
            </urlReviewData>
            <adGroupAdRotationMode>
              <adRotationMode>OPTIMIZE</adRotationMode>
            </adGroupAdRotationMode>
          </adGroup>
        </values>
      </rval>
    </mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告グループを削除します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | 操作の対象となる広告グループと処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V6">
      <license xmlns="">1111-1111-1111-1111</license>
      <apiAccountId xmlns="">2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword xmlns="">password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V6">
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
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含む広告グループに関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">AdGroup</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutateResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <ListReturnValue.Type>AdGroupReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <adGroup>
            <accountId>1234567890</accountId>
            <campaignId>10001</campaignId>
            <campaignTrackId>100000001</campaignTrackId>
            <campaignName>test campaign.</campaignName>
            <adGroupId>20001</adGroupId>
            <adGroupTrackId>0</adGroupTrackId>
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
            <urlReviewData>
              <urlApprovalStatus>APPROVED</urlApprovalStatus>
            </urlReviewData>
            <adGroupAdRotationMode>
              <adRotationMode>OPTIMIZE</adRotationMode>
            </adGroupAdRotationMode>
          </adGroup>
        </values>
      </rval>
    </mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
