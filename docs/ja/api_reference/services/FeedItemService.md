# FeedItemService
FeedItemServiceでは、フィードアイテム情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V6.0/FeedItemService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V6.0/FeedItemService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
フィードアイテム情報の取得および追加・更新・削除を行います。

#### 操作
FeedItemServiceで提供される操作を説明します。

## get
フィードアイテム情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [FeedItemSelector](../data/FeedItemSelector.md) | 操作の対象とするフィードアイテム情報です。 | 

＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:feedItemIds>12</ns1:feedItemIds>
        <ns1:feedItemIds>13</ns1:feedItemIds>
        <ns1:placeholderTypes>QUICKLINK</ns1:placeholderTypes>
        <ns1:placeholderTypes>CALLEXTENSION</ns1:placeholderTypes>
        <ns1:placeholderTypes>AD_CUSTOMIZER</ns1:placeholderTypes>
        <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
        <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
        <ns1:advanced>TRUE</ns1:advanced>
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>20</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [FeedItemPage](../data/FeedItemPage.md) | 取得されるフィードアイテム情報に関するエントリーです。 | 

＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>FeedItemService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>3</ns1:totalNumEntries>
        <ns1:Page.Type>FeedItemPage</ns1:Page.Type>
        <!-- 配信中 -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000000</ns1:feedItemId>
            <ns1:feedItemTrackId>3000000000</ns1:feedItemTrackId>
            <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            <ns1:startDate>20120112</ns1:startDate>
            <ns1:endDate>20120113</ns1:endDate>
            <ns1:scheduling>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
            </ns1:scheduling>
            <ns1:customParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:customParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
        <!-- 編集内容審査中 -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000001</ns1:feedItemId>
            <ns1:feedItemTrackId>3000000001</ns1:feedItemTrackId>
            <ns1:approvalStatus>APPROVED_WITH_REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:feedAttributeValue>
              <ns1:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}
              </ns1:reviewFeedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            <ns1:startDate>20120112</ns1:startDate>
            <ns1:endDate>20120113</ns1:endDate>
            <ns1:scheduling>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
            </ns1:scheduling>
            <ns1:customParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:customParameters>
            <ns1:reviewCustomParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>mysite</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>5678</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>jFj903Hng8e</ns1:value>
              </ns1:parameters>
            </ns1:reviewCustomParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
        <!-- 掲載停止 -->
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000000</ns1:feedItemId>
            <ns1:feedItemTrackId>3000000000</ns1:feedItemTrackId>
            <ns1:approvalStatus>POST_DISAPPROVED</ns1:approvalStatus>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            <ns1:startDate>20120112</ns1:startDate>
            <ns1:endDate>20120113</ns1:endDate>
            <ns1:scheduling>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
            </ns1:scheduling>
            <ns1:customParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:customParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
フィードアイテム情報を追加します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [FeedItemOperation](../data/FeedItemOperation.md) | 操作の対象とするフィードアイテム情報と処理の内容です。 | 

＜リクエストサンプル＞ 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
        <ns1:operand>
          <ns1:feedItemAttribute>
            <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute>
            <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute>
            <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
          <ns1:scheduling>
            <ns1:schedules>
              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
              <ns1:startHour>14</ns1:startHour>
              <ns1:startMinute>ZERO</ns1:startMinute>
              <ns1:endHour>15</ns1:endHour>
              <ns1:endMinute>FIFTEEN</ns1:endMinute>
            </ns1:schedules>
          </ns1:scheduling>
          <ns1:customParameters>
            <ns1:isRemove>FALSE</ns1:isRemove>
            <ns1:parameters>
              <ns1:key>site</ns1:key>
              <ns1:value>yahoo</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id1</ns1:key>
              <ns1:value>1234</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id2</ns1:key>
              <ns1:value>a7h59A98yu</ns1:value>
            </ns1:parameters>
          </ns1:customParameters>
          <ns1:advanced>TRUE</ns1:advanced>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | 操作結果を含むフィードアイテム情報のコンテナです。 | 

＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>FeedItemService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.285</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000001</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}
              </ns1:reviewFeedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            <ns1:startDate>20120112</ns1:startDate>
            <ns1:endDate>20120113</ns1:endDate>
            <ns1:scheduling>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
            </ns1:scheduling>
            <ns1:reviewCustomParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:reviewCustomParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [FeedItemOperation](../data/FeedItemOperation.md) | 操作の対象とするFeedItem情報です。 | 

＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>SET</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
        <ns1:operand>
          <ns1:feedItemId>200000001</ns1:feedItemId>
          <ns1:feedItemAttribute>
            <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute>
            <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:feedItemAttribute>
            <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
            <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}</ns1:feedAttributeValue>
          </ns1:feedItemAttribute>
          <ns1:startDate>20151231</ns1:startDate>
          <ns1:endDate>20200101</ns1:endDate>
          <ns1:scheduling>
            <ns1:schedules>
              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
              <ns1:startHour>14</ns1:startHour>
              <ns1:startMinute>ZERO</ns1:startMinute>
              <ns1:endHour>15</ns1:endHour>
              <ns1:endMinute>FIFTEEN</ns1:endMinute>
            </ns1:schedules>
          </ns1:scheduling>
          <ns1:customParameters>
            <ns1:isRemove>FALSE</ns1:isRemove>
            <ns1:parameters>
              <ns1:key>site</ns1:key>
              <ns1:value>mysite</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id1</ns1:key>
              <ns1:value>5678</ns1:value>
            </ns1:parameters>
            <ns1:parameters>
              <ns1:key>id2</ns1:key>
              <ns1:value>jFj903Hng8e</ns1:value>
            </ns1:parameters>
          </ns1:customParameters>
          <ns1:advanced>TRUE</ns1:advanced>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | 操作結果を含むフィードアイテム情報のコンテナです。 | 

＜レスポンスサンプル＞ 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>FeedItemService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.285</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000001</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:feedAttributeValue>
              <ns1:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;uid={id1}&amp;xid={id2}
              </ns1:reviewFeedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            <ns1:startDate>20120112</ns1:startDate>
            <ns1:endDate>20120113</ns1:endDate>
            <ns1:scheduling>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
            </ns1:scheduling>
            <ns1:customParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:customParameters>
            <ns1:reviewCustomParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>mysite</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>5678</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>jFj903Hng8e</ns1:value>
              </ns1:parameters>
            </ns1:reviewCustomParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
フィードアイテム情報を削除します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [FeedItemOperation](../data/FeedItemOperation.md) | 操作の対象とする情報です。 | 

＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>REMOVE</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
        <ns1:operand>
          <ns1:feedItemId>113</ns1:feedItemId>
        </ns1:operand>
        <ns1:operand>
          <ns1:feedItemId>114</ns1:feedItemId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [FeedItemReturnValue](../data/FeedItemReturnValue.md) | 取得されるフィードアイテム情報に関するエントリーです。 |

＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>FeedItemService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.285</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>FeedItemReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:feedItem>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:feedItemId>200000001</ns1:feedItemId>
            <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://www.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>ADVANCED_MOBILE_URL</ns1:placeholderField>
              <ns1:feedAttributeValue>http://portal.mobile.yahoo.co.jp</ns1:feedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:feedItemAttribute>
              <ns1:placeholderField>TRACKING_URL</ns1:placeholderField>
              <ns1:reviewFeedAttributeValue>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}
              </ns1:reviewFeedAttributeValue>
            </ns1:feedItemAttribute>
            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
            <ns1:startDate>20120112</ns1:startDate>
            <ns1:endDate>20120113</ns1:endDate>
            <ns1:scheduling>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
              <ns1:schedules>
                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                <ns1:startHour>12</ns1:startHour>
                <ns1:startMinute>ZERO</ns1:startMinute>
                <ns1:endHour>13</ns1:endHour>
                <ns1:endMinute>FIFTEEN</ns1:endMinute>
              </ns1:schedules>
            </ns1:scheduling>
            <ns1:reviewCustomParameters>
              <ns1:isRemove>FALSE</ns1:isRemove>
              <ns1:parameters>
                <ns1:key>site</ns1:key>
                <ns1:value>yahoo</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id1</ns1:key>
                <ns1:value>1234</ns1:value>
              </ns1:parameters>
              <ns1:parameters>
                <ns1:key>id2</ns1:key>
                <ns1:value>a7h59A98yu</ns1:value>
              </ns1:parameters>
            </ns1:reviewCustomParameters>
            <ns1:advanced>TRUE</ns1:advanced>
          </ns1:feedItem>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
