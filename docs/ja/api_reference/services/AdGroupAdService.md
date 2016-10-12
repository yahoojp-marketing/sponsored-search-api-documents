# AdGroupAdService
AdGroupAdServiceでは、広告に関する情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
広告に関する情報の取得および追加・更新・削除を行います。　

#### 操作
AdGroupAdServiceで提供される操作を説明します。
<br>

## get
広告に関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupAdSelector](../data/AdGroupAdSelector.md) | 操作の対象とする広告に関する情報です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
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
                <ns1:campaignIds>100000001</ns1:campaignIds>
                <ns1:campaignIds>100000002</ns1:campaignIds>
                <ns1:adGroupIds>100000001</ns1:adGroupIds>
                <ns1:adGroupIds>100000002</ns1:adGroupIds>
                <ns1:adGroupIds>100000003</ns1:adGroupIds>
                <ns1:adGroupIds>100000004</ns1:adGroupIds>
                <ns1:adIds>100000001</ns1:adIds>
                <ns1:adIds>100000002</ns1:adIds>
                <ns1:adIds>100000003</ns1:adIds>
                <ns1:adIds>100000004</ns1:adIds>
                <ns1:adTypes>TEXT_AD2</ns1:adTypes>
                <ns1:adTypes>APP_AD</ns1:adTypes>
                <ns1:adTypes>EXTENDED_TEXT_AD</ns1:adTypes>
                <ns1:userStatuses>ACTIVE</ns1:userStatuses>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>APPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>PRE_DISAPPROVED</ns1:approvalStatuses>
                <ns1:approvalStatuses>POST_DISAPPROVED</ns1:approvalStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdPage](../data/AdGroupAdPage.md) | 取得される広告に関するエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>4</ns1:totalNumEntries>
                <ns1:Page.Type>AdGroupAdPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>テキスト広告グループ</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>テキスト広告2</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>カウントダウン</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>アプリ広告グループ</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>アプリ広告</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:headline>アプリ広告タイトル</ns1:headline>
                            <ns1:description>アプリ広告の説明文1</ns1:description>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                            <ns1:description2>アプリ広告の説明文2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>広告グループ</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>広告LPO</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://yahoo.co.jp/sample/url</ns1:advancedUrl>
                            <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/url1</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>
                            <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/url2</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>
                             <ns1:additionalAdvancedUrls>
                               <ns1:advancedUrl>http://yahoo.co.jp/sample/url3</ns1:advancedUrl>
                            </ns1:additionalAdvancedUrls>                          
                            <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/url</ns1:advancedMobileUrl>
                            <ns1:additionalAdvancedMobileUrls>
                               <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/url1</ns1:advancedMobileUrl>
                            </ns1:additionalAdvancedMobileUrls>
                             <ns1:additionalAdvancedMobileUrls>
                               <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/url2</ns1:advancedMobileUrl>
                            </ns1:additionalAdvancedMobileUrls>                          
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:headline>アプリ広告タイトル</ns1:headline>
                            <ns1:description>アプリ広告の説明文1</ns1:description>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                            <ns1:description2>アプリ広告の説明文2</ns1:description2>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>               
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>テキスト広告グループ</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>テキスト広告2</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:ExtendedTextAd">
                            <ns1:type>EXTENDED_TEXT_AD</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>タイトル１</ns1:headline>
                            <ns1:description>説明文</ns1:description>
                            <ns1:headline2>タイトル２</ns1:headline2>
                            <ns1:path1>addtional displayUrl1</ns1:path1>
                            <ns1:path2>addtional displayUrl2</ns1:path2>
                        </ns1:ad>
                   </ns1:adGroupAd>
                </ns1:values>              
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
広告に関する情報を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | 操作の対象となる広告と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000001</ns1:adGroupId>
               <ns1:adName>テキスト広告</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:TextAd2">
                  <ns1:type>TEXT_AD2</ns1:type>
                  <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                  <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
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
                  <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                  <ns1:headline>タイトル</ns1:headline>
                  <ns1:description>カウントダウン</ns1:description>
                  <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
               </ns1:ad>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000003</ns1:adGroupId>
               <ns1:adName>アプリ広告</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:AppAd">
                  <ns1:type>APP_AD</ns1:type>
                  <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                  <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
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
                  <ns1:headline>アプリ広告タイトル</ns1:headline>
                  <ns1:description>アプリ広告の説明文1</ns1:description>
                  <ns1:description2>アプリ広告の説明文2</ns1:description2>
                  <ns1:appStore>IOS</ns1:appStore>
                  <ns1:appId>appid1234567890</ns1:appId>
               </ns1:ad>
            </ns1:operand>
            <ns1:operand>
               <ns1:campaignId>100000001</ns1:campaignId>
               <ns1:adGroupId>100000001</ns1:adGroupId>
               <ns1:adName>テキスト広告</ns1:adName>
               <ns1:userStatus>ACTIVE</ns1:userStatus>
               <ns1:ad xsi:type="ns1:ExtendedTextAd">
                  <ns1:type>EXTENDED_TEXT_AD</ns1:type>
                  <ns1:advancedUrl>http://yahoo.co.jp/url</ns1:advancedUrl>
                 <ns1:advancedMobileUrl>http://yahoo.co.jp/mobile/url</ns1:advancedMobileUrl>
                  <ns1:trackingUrl><![CDATA[http://yahoo.co.jp?url={lpurl}&c={campaignid}&g={adgroupid}&a={creative}&type={site}&pid={id1}&vid={id2}]]></ns1:trackingUrl>
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
                 <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                  <ns1:headline>タイトル</ns1:headline>
                  <ns1:description>説明文</ns1:description>
                  <ns1:headline2>タイトル2</ns1:headline2>
                  <ns1:path1>addtional displayUrl1</ns1:path1>
                  <ns1:path2>addtional displayUrl2</ns1:path2>
               </ns1:ad>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | 操作結果を含む広告に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>テキスト広告グループ</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>テキスト広告2</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>カウントダウン</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>アプリ広告グループ</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>アプリ広告</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:headline>アプリ広告タイトル</ns1:headline>
                            <ns1:description>アプリ広告の説明文1</ns1:description>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                            <ns1:description2>アプリ広告の説明文2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>広告グループ</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>広告</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:ExtendedTextAd">
                            <ns1:type>EXTENDED_TEXT_AD</ns1:type>
                            <ns1:advancedUrl>http://yahoo.co.jp/sample/lpo</ns1:advancedUrl>
                           <ns1:advancedMobileUrl>http://yahoo.co.jp/sample/mobile/lpo</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:headline>タイトル１</ns1:headline>
                            <ns1:description>説明文</ns1:description>
                            <ns1:headline2>タイトル２</ns1:headline2>
                            <ns1:path1>addtional displayUrl1</ns1:path1>
                            <ns1:path2>addtional displayUrl2</ns1:path2>   
                       </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>               
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告に関する情報を更新します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | 操作の対象となる広告と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000001</ns1:adGroupId>
                    <ns1:adId>100000002</ns1:adId>
                    <ns1:adName>テキスト広告2更新</ns1:adName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                </ns1:operand>
                <ns1:operand>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000003</ns1:adGroupId>
                    <ns1:adId>100000003</ns1:adId>
                    <ns1:adName>アプリ広告更新</ns1:adName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | 操作結果を含む広告に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>テキスト広告グループ</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>テキスト広告2</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>カウントダウン</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>アプリ広告グループ</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>アプリ広告</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:headline>アプリ広告タイトル</ns1:headline>
                            <ns1:description>アプリ広告の説明文1</ns1:description>
                            <ns1:description2>アプリ広告の説明文2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告に関する情報を削除します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | 操作の対象となる広告と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000001</ns1:adGroupId>
                    <ns1:adId>100000002</ns1:adId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000001</ns1:campaignId>
                    <ns1:adGroupId>100000002</ns1:adGroupId>
                    <ns1:adId>100000003</ns1:adId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | 操作結果を含む広告に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:ns1="http://ss.yahooapis.jp/V6"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000001</ns1:adGroupId>
                        <ns1:adGroupTrackId>222222</ns1:adGroupTrackId>
                        <ns1:adGroupName>テキスト広告グループ</ns1:adGroupName>
                        <ns1:adId>100000002</ns1:adId>
                        <ns1:adTrackId>333333</ns1:adTrackId>
                        <ns1:adName>テキスト広告2</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:TextAd2">
                            <ns1:type>TEXT_AD2</ns1:type>
                            <ns1:advancedUrl>http://aaaa.jp</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://aaaa.jp/mb</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>カウントダウン</ns1:description>
                            <ns1:description2>{=COUNTDOWN("2016/01/01 00:00:00","ja")}</ns1:description2>
                        </ns1:ad>
                        <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    </ns1:adGroupAd>
                </ns1:values>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>100000001</ns1:accountId>
                        <ns1:campaignId>100000001</ns1:campaignId>
                        <ns1:campaignTrackId>111111</ns1:campaignTrackId>
                        <ns1:campaignName>キャンペーン</ns1:campaignName>
                        <ns1:adGroupId>100000003</ns1:adGroupId>
                        <ns1:adGroupTrackId>444444</ns1:adGroupTrackId>
                        <ns1:adGroupName>アプリ広告グループ</ns1:adGroupName>
                        <ns1:adId>100000004</ns1:adId>
                        <ns1:adTrackId>555555</ns1:adTrackId>
                        <ns1:adName>アプリ広告</ns1:adName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:ad xsi:type="ns1:AppAd">
                            <ns1:type>APP_AD</ns1:type>
                            <ns1:advancedUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedUrl>
                            <ns1:advancedMobileUrl>http://www.apple.com/jp/itunes/app/appname/appid1234567890</ns1:advancedMobileUrl>
                            <ns1:trackingUrl>http://yahoo.co.jp?url={lpurl}&amp;c={campaignid}&amp;g={adgroupid}&amp;a={creative}&amp;type={site}&amp;pid={id1}&amp;vid={id2}</ns1:trackingUrl>
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
                            <ns1:headline>アプリ広告タイトル</ns1:headline>
                            <ns1:description>アプリ広告の説明文1</ns1:description>
                            <ns1:description2>アプリ広告の説明文2</ns1:description2>
                            <ns1:appStore>IOS</ns1:appStore>
                            <ns1:appId>appid1234567890</ns1:appId>
                            <ns1:devicePreference>SMART_PHONE</ns1:devicePreference>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
