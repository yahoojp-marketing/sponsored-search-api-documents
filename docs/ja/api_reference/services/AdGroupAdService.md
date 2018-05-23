# AdGroupAdService
AdGroupAdServiceでは、広告に関する情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/AdGroupAdService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201805/AdGroupAd

#### サービス概要
広告に関する情報の取得および追加・更新・削除を行います。　

#### 操作
AdGroupAdServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)


#### オブジェクト
[AdGroupAd](../data/AdGroupAd)

## get
広告に関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AdGroupAdSelector](../data/AdGroupAd/AdGroupAdSelector.md) | 操作の対象とする広告に関する情報です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>1234567890</accountId>
        <campaignIds>20001</campaignIds>
        <campaignIds>20002</campaignIds>
        <campaignIds>20003</campaignIds>
        <campaignIds>20004</campaignIds>
        <campaignIds>20005</campaignIds>
        <adGroupIds>30001</adGroupIds>
        <adGroupIds>30002</adGroupIds>
        <adGroupIds>30003</adGroupIds>
        <adGroupIds>30004</adGroupIds>
        <adGroupIds>30005</adGroupIds>
        <adIds>40001</adIds>
        <adIds>40002</adIds>
        <adIds>40003</adIds>
        <adIds>40004</adIds>
        <adIds>40005</adIds>
        <adTypes>TEXT_AD2</adTypes>
        <adTypes>APP_AD</adTypes>
        <adTypes>EXTENDED_TEXT_AD</adTypes>
        <userStatuses>ACTIVE</userStatuses>
        <userStatuses>PAUSED</userStatuses>
        <approvalStatuses>APPROVED</approvalStatuses>
        <approvalStatuses>APPROVED_WITH_REVIEW</approvalStatuses>
        <approvalStatuses>REVIEW</approvalStatuses>
        <approvalStatuses>PRE_DISAPPROVED</approvalStatuses>
        <approvalStatuses>POST_DISAPPROVED</approvalStatuses>
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
| rval | [AdGroupAdPage](../data/AdGroupAd/AdGroupAdPage.md) | 取得される広告に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1523506328386</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroupAd">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <Page.Type>AdGroupAdPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignTrackId>200000001</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupTrackId>300000001</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40001</ns2:adId>
            <ns2:adTrackId>400000001</ns2:adTrackId>
            <ns2:adName>sample text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd2">
              <ns2:type>TEXT_AD2</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:additionalAdvancedUrls>
                <ns2:advancedUrl>http://yahoo.co.jp/url1</ns2:advancedUrl>
              </ns2:additionalAdvancedUrls>
              <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp</ns2:advancedMobileUrl>
              <ns2:additionalAdvancedMobileUrls>
                <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp/url1</ns2:advancedMobileUrl>
              </ns2:additionalAdvancedMobileUrls>
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
              <ns2:displayUrl>yahoo.co.jp</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns2:description2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20002</ns2:campaignId>
            <ns2:campaignTrackId>200000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30002</ns2:adGroupId>
            <ns2:adGroupTrackId>300000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40002</ns2:adId>
            <ns2:adTrackId>400000002</ns2:adTrackId>
            <ns2:adName>sample app ad for ios.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>itunes.apple.com</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>IOS</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20003</ns2:campaignId>
            <ns2:campaignTrackId>200000003</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30003</ns2:adGroupId>
            <ns2:adGroupTrackId>300000003</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40003</ns2:adId>
            <ns2:adTrackId>400000003</ns2:adTrackId>
            <ns2:adName>sample app ad for android.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>https://play.google.com/store/apps/details?id=appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>play.google.com/store</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>ANDROID</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20004</ns2:campaignId>
            <ns2:campaignTrackId>200000004</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30004</ns2:adGroupId>
            <ns2:adGroupTrackId>300000004</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40004</ns2:adId>
            <ns2:adTrackId>400000004</ns2:adTrackId>
            <ns2:adName>sample extended text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ExtendedTextAd">
              <ns2:type>EXTENDED_TEXT_AD</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:displayUrl>yahoo.co.jp/path1/path2</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:headline2>sample ad title2.</ns2:headline2>
              <ns2:path1>path1</ns2:path1>
              <ns2:path2>path2</ns2:path2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
広告に関する情報を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) | 操作の対象となる広告と処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adName>sample text ad.</adName>
          <userStatus>ACTIVE</userStatus>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="TextAd2">
            <type>TEXT_AD2</type>
            <advancedUrl>http://yahoo.co.jp</advancedUrl>
            <additionalAdvancedUrls>
              <advancedUrl>http://yahoo.co.jp/url1</advancedUrl>
            </additionalAdvancedUrls>
            <advancedMobileUrl>http://mobile.yahoo.co.jp</advancedMobileUrl>
            <additionalAdvancedMobileUrls>
              <advancedMobileUrl>http://mobile.yahoo.co.jp/url1</advancedMobileUrl>
            </additionalAdvancedMobileUrls>
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
            <displayUrl>yahoo.co.jp</displayUrl>
            <headline>sample ad title.</headline>
            <description>sample ad description.</description>
            <devicePreference>SMART_PHONE</devicePreference>
            <description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</description2>
          </ad>
        </operand>
        <operand>
          <campaignId>20002</campaignId>
          <adGroupId>30002</adGroupId>
          <adName>sample app ad for ios.</adName>
          <userStatus>ACTIVE</userStatus>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppAd">
            <type>APP_AD</type>
            <advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</advancedUrl>
            <displayUrl>itunes.apple.com</displayUrl>
            <headline>sample ad title.</headline>
            <description>sample ad description.</description>
            <description2>sample ad description2.</description2>
            <appStore>IOS</appStore>
            <appId>appid1234567890</appId>
          </ad>
        </operand>
        <operand>
          <campaignId>20003</campaignId>
          <adGroupId>30003</adGroupId>
          <adName>sample app ad for android.</adName>
          <userStatus>ACTIVE</userStatus>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppAd">
            <type>APP_AD</type>
            <advancedUrl>https://play.google.com/store/apps/details?id=appid1234567890</advancedUrl>
            <displayUrl>play.google.com/store</displayUrl>
            <headline>sample ad title.</headline>
            <description>sample ad description.</description>
            <description2>sample ad description2.</description2>
            <appStore>ANDROID</appStore>
            <appId>appid1234567890</appId>
          </ad>
        </operand>
        <operand>
          <campaignId>20004</campaignId>
          <adGroupId>30004</adGroupId>
          <adName>sample extended text ad.</adName>
          <userStatus>ACTIVE</userStatus>
          <ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ExtendedTextAd">
            <type>EXTENDED_TEXT_AD</type>
            <advancedUrl>http://yahoo.co.jp</advancedUrl>
            <displayUrl>yahoo.co.jp/path1/path2</displayUrl>
            <headline>sample ad title.</headline>
            <description>sample ad description.</description>
            <devicePreference>SMART_PHONE</devicePreference>
            <headline2>sample ad title2.</headline2>
            <path1>path1</path1>
            <path2>path2</path2>
          </ad>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) | 操作結果を含む広告に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1523506328423</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignTrackId>200000001</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupTrackId>300000001</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40001</ns2:adId>
            <ns2:adTrackId>400000001</ns2:adTrackId>
            <ns2:adName>sample text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd2">
              <ns2:type>TEXT_AD2</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:additionalAdvancedUrls>
                <ns2:advancedUrl>http://yahoo.co.jp/url1</ns2:advancedUrl>
              </ns2:additionalAdvancedUrls>
              <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp</ns2:advancedMobileUrl>
              <ns2:additionalAdvancedMobileUrls>
                <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp/url1</ns2:advancedMobileUrl>
              </ns2:additionalAdvancedMobileUrls>
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
              <ns2:displayUrl>yahoo.co.jp</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns2:description2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20002</ns2:campaignId>
            <ns2:campaignTrackId>200000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30002</ns2:adGroupId>
            <ns2:adGroupTrackId>300000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40002</ns2:adId>
            <ns2:adTrackId>400000002</ns2:adTrackId>
            <ns2:adName>sample app ad for ios.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>itunes.apple.com</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>IOS</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20003</ns2:campaignId>
            <ns2:campaignTrackId>200000003</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30003</ns2:adGroupId>
            <ns2:adGroupTrackId>300000003</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40003</ns2:adId>
            <ns2:adTrackId>400000003</ns2:adTrackId>
            <ns2:adName>sample app ad for android.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>https://play.google.com/store/apps/details?id=appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>play.google.com/store</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>ANDROID</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20004</ns2:campaignId>
            <ns2:campaignTrackId>200000004</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30004</ns2:adGroupId>
            <ns2:adGroupTrackId>300000004</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40004</ns2:adId>
            <ns2:adTrackId>400000004</ns2:adTrackId>
            <ns2:adName>sample extended text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ExtendedTextAd">
              <ns2:type>EXTENDED_TEXT_AD</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:displayUrl>yahoo.co.jp/path1/path2</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:headline2>sample ad title2.</ns2:headline2>
              <ns2:path1>path1</ns2:path1>
              <ns2:path2>path2</ns2:path2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告に関する情報を更新します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) | 操作の対象となる広告と処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adGroupName>sample text ad.</adGroupName>
          <adId>40001</adId>
          <userStatus>ACTIVE</userStatus>
        </operand>
        <operand>
          <campaignId>20002</campaignId>
          <adGroupId>30002</adGroupId>
          <adId>40002</adId>
          <adName>sample app ad for ios.</adName>
          <userStatus>ACTIVE</userStatus>
        </operand>
        <operand>
          <campaignId>20003</campaignId>
          <adGroupId>30003</adGroupId>
          <adId>40003</adId>
          <adName>sample app ad for android.</adName>
          <userStatus>ACTIVE</userStatus>
        </operand>
        <operand>
          <campaignId>20004</campaignId>
          <adGroupId>30004</adGroupId>
          <adId>40004</adId>
          <adName>sample extended text ad.</adName>
          <userStatus>ACTIVE</userStatus>
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
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) | 操作結果を含む広告に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1523506328469</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignTrackId>200000001</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupTrackId>300000001</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40001</ns2:adId>
            <ns2:adTrackId>400000001</ns2:adTrackId>
            <ns2:adName>sample text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd2">
              <ns2:type>TEXT_AD2</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:additionalAdvancedUrls>
                <ns2:advancedUrl>http://yahoo.co.jp/url1</ns2:advancedUrl>
              </ns2:additionalAdvancedUrls>
              <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp</ns2:advancedMobileUrl>
              <ns2:additionalAdvancedMobileUrls>
                <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp/url1</ns2:advancedMobileUrl>
              </ns2:additionalAdvancedMobileUrls>
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
              <ns2:displayUrl>yahoo.co.jp</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns2:description2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20002</ns2:campaignId>
            <ns2:campaignTrackId>200000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30002</ns2:adGroupId>
            <ns2:adGroupTrackId>300000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40002</ns2:adId>
            <ns2:adTrackId>400000002</ns2:adTrackId>
            <ns2:adName>sample app ad for ios.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>itunes.apple.com</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>IOS</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20003</ns2:campaignId>
            <ns2:campaignTrackId>200000003</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30003</ns2:adGroupId>
            <ns2:adGroupTrackId>300000003</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40003</ns2:adId>
            <ns2:adTrackId>400000003</ns2:adTrackId>
            <ns2:adName>sample app ad for android.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>https://play.google.com/store/apps/details?id=appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>play.google.com/store</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>ANDROID</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20004</ns2:campaignId>
            <ns2:campaignTrackId>200000004</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30004</ns2:adGroupId>
            <ns2:adGroupTrackId>300000004</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40004</ns2:adId>
            <ns2:adTrackId>400000004</ns2:adTrackId>
            <ns2:adName>sample extended text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ExtendedTextAd">
              <ns2:type>EXTENDED_TEXT_AD</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:displayUrl>yahoo.co.jp/path1/path2</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:headline2>sample ad title2.</ns2:headline2>
              <ns2:path1>path1</ns2:path1>
              <ns2:path2>path2</ns2:path2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告に関する情報を削除します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAd/AdGroupAdOperation.md) | 操作の対象となる広告と処理の内容です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>20001</campaignId>
          <adGroupId>30001</adGroupId>
          <adId>40001</adId>
        </operand>
        <operand>
          <campaignId>20002</campaignId>
          <adGroupId>30002</adGroupId>
          <adId>40002</adId>
        </operand>
        <operand>
          <campaignId>20003</campaignId>
          <adGroupId>30003</adGroupId>
          <adId>40003</adId>
        </operand>
        <operand>
          <campaignId>20004</campaignId>
          <adGroupId>30004</adGroupId>
          <adId>40004</adId>
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
| rval | [AdGroupAdReturnValue](../data/AdGroupAd/AdGroupAdReturnValue.md) | 操作結果を含む広告に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AdGroupAd" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AdGroupAd</ns2:service>
      <ns2:requestTime>1523506328509</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AdGroupAd">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupAdReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20001</ns2:campaignId>
            <ns2:campaignTrackId>200000001</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30001</ns2:adGroupId>
            <ns2:adGroupTrackId>300000001</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40001</ns2:adId>
            <ns2:adTrackId>400000001</ns2:adTrackId>
            <ns2:adName>sample text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:TextAd2">
              <ns2:type>TEXT_AD2</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:additionalAdvancedUrls>
                <ns2:advancedUrl>http://yahoo.co.jp/url1</ns2:advancedUrl>
              </ns2:additionalAdvancedUrls>
              <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp</ns2:advancedMobileUrl>
              <ns2:additionalAdvancedMobileUrls>
                <ns2:advancedMobileUrl>http://mobile.yahoo.co.jp/url1</ns2:advancedMobileUrl>
              </ns2:additionalAdvancedMobileUrls>
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
              <ns2:displayUrl>yahoo.co.jp</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns2:description2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20002</ns2:campaignId>
            <ns2:campaignTrackId>200000002</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30002</ns2:adGroupId>
            <ns2:adGroupTrackId>300000002</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40002</ns2:adId>
            <ns2:adTrackId>400000002</ns2:adTrackId>
            <ns2:adName>sample app ad for ios.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>itunes.apple.com</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>IOS</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20003</ns2:campaignId>
            <ns2:campaignTrackId>200000003</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30003</ns2:adGroupId>
            <ns2:adGroupTrackId>300000003</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40003</ns2:adId>
            <ns2:adTrackId>400000003</ns2:adTrackId>
            <ns2:adName>sample app ad for android.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppAd">
              <ns2:type>APP_AD</ns2:type>
              <ns2:advancedUrl>https://play.google.com/store/apps/details?id=appid1234567890</ns2:advancedUrl>
              <ns2:displayUrl>play.google.com/store</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:description2>sample ad description2.</ns2:description2>
              <ns2:appStore>ANDROID</ns2:appStore>
              <ns2:appId>appid1234567890</ns2:appId>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupAd>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>20004</ns2:campaignId>
            <ns2:campaignTrackId>200000004</ns2:campaignTrackId>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
            <ns2:adGroupId>30004</ns2:adGroupId>
            <ns2:adGroupTrackId>300000004</ns2:adGroupTrackId>
            <ns2:adGroupName>sample adGroup.</ns2:adGroupName>
            <ns2:adId>40004</ns2:adId>
            <ns2:adTrackId>400000004</ns2:adTrackId>
            <ns2:adName>sample extended text ad.</ns2:adName>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:ExtendedTextAd">
              <ns2:type>EXTENDED_TEXT_AD</ns2:type>
              <ns2:advancedUrl>http://yahoo.co.jp</ns2:advancedUrl>
              <ns2:displayUrl>yahoo.co.jp/path1/path2</ns2:displayUrl>
              <ns2:headline>sample ad title.</ns2:headline>
              <ns2:description>sample ad description.</ns2:description>
              <ns2:devicePreference>SMART_PHONE</ns2:devicePreference>
              <ns2:headline2>sample ad title2.</ns2:headline2>
              <ns2:path1>path1</ns2:path1>
              <ns2:path2>path2</ns2:path2>
            </ns2:ad>
          </ns2:adGroupAd>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
