# ConversionTrackerService
ConversionTrackerServiceでは、コンバージョントラッカー情報の取得および追加・更新を行います。<br>
コンバージョントラッカー情報とは、コンバージョン測定タグおよびタグごとのパフォーマンスデータを表します。<br>
本サービスを利用することで、スポンサードサーチで掲載されている広告からのコンバージョン数（商品の購入や会員登録、資料請求などサイト上で何らかの成約に至った件数）を取得することができ、広告がどの程度成果を上げているかなどを確認できます。<br>
コンバージョンタグは広告管理ツールとAPIで共有しています。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/ConversionTrackerService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/ConversionTrackerService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### サービス概要
コンバージョントラッカー情報の取得、追加、更新を行います。
#### 注意事項
ConversionTrackerServiceには以下の注意事項があります。<br>
* コンバージョン測定は、アカウントごとにウェブページ・電話発信・アプリダウンロードの3種類あわせて1,000件まで設定可能です。
* 一度作成したコンバージョン測定タグは削除できません。新たなタグを作成するか、作成したタグを変更してご利用ください。
* コンバージョン測定は、クッキー情報を元に実施します。
* 2016年11月16日以降にコンバージョン測定タグを追加・編集する場合は、測定期間を7～90日間で設定できます。<br>なお、アプリダウンロード広告の場合、測定期間は30日間固定です。
* 電話発信コンバージョンの測定のためには、お客様のサイト内に「コンバージョン測定タグ」と「オンクリックイベントタグ」を設置する必要があります。<br>「オンクリックイベントタグ」の設置方法は、スポンサードサーチのヘルプをご確認ください。<br>
https://help.marketing.yahoo.co.jp/ja/?p=1169<br>

その他、コンバージョン測定の詳細は、スポンサードサーチのヘルプをご参照ください。<br>
http://help.marketing.yahoo.co.jp/ja/?p=1161<br>
## get
コンバージョントラッカー情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ConversionTrackerSelector](../data/ConversionTrackerSelector.md) | 操作の対象とするコンバージョントラッカー情報の設定です。 | 
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
        <accountId>1111</accountId>
        <conversionTrackerIds>222</conversionTrackerIds>
        <conversionTrackerIds>333</conversionTrackerIds>
        <conversionTrackerIds>444</conversionTrackerIds>
        <conversionTrackerIds>555</conversionTrackerIds>
        <conversionTrackerIds>666</conversionTrackerIds>
        <appIds>aaaaa</appIds>
        <appIds>bbbbb</appIds>
        <appIds>ccccc</appIds>
        <appIds>ddddd</appIds>
        <appIds>eeeee</appIds>
        <statuses>ENABLED</statuses>
        <statuses>DISABLED</statuses>
        <categories>DEFAULT</categories>
        <categories>PAGE_VIEW</categories>
        <categories>PURCHASE</categories>
        <categories>SIGNUP</categories>
        <categories>LEAD</categories>
        <categories>DOWNLOAD</categories>
        <conversionTrackerTypes>WEB_CONVERSION</conversionTrackerTypes>
        <conversionTrackerTypes>APP_CONVERSION</conversionTrackerTypes>
        <trackingCodeTypes>WEBPAGE</trackingCodeTypes>
        <trackingCodeTypes>CLICK_TO_CALL</trackingCodeTypes>
        <countingTypes>ONE_PER_CLICK</countingTypes>
        <countingTypes>MANY_PER_CLICK</countingTypes>
        <excludeFromBiddings>TRUE</excludeFromBiddings>
        <excludeFromBiddings>FALSE</excludeFromBiddings>
        <crossDeviceConversionFlags>TRUE</crossDeviceConversionFlags>
        <crossDeviceConversionFlags>FALSE</crossDeviceConversionFlags>
        <dateRange>
          <startDate>19700101</startDate>
          <endDate>20371231</endDate>
        </dateRange>
        <paging>
          <startIndex>1</startIndex>
          <numberResults>10</numberResults>
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
| rval | [ConversionTrackerPage](../data/ConversionTrackerPage.md) | 取得されるコンバージョントラッカー情報に関するエントリーです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">ConversionTracker</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <totalNumEntries>4</totalNumEntries>
        <totalConversions>20</totalConversions>
        <totalAllConversions>50</totalAllConversions>
        <totalConversionValue>20</totalConversionValue>
        <totalAllConversionValue>50</totalAllConversionValue>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193198</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DEFAULT</category>
            <conversions>0</conversions>
            <conversionValue>0</conversionValue>
            <allConversions>10</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>100</userRevenueValue>
            <countingType>MANY_PER_CLICK</countingType>
            <excludeFromBidding>TRUE</excludeFromBidding>
            <measurementPeriod>30</measurementPeriod>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>IN_APP_PURCHASE</appConversionType>
            <snippetId>1000661</snippetId>
            <snippetLabel>XXXXXXXXXXXXXXXXXX</snippetLabel>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193197</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_FIRST_OPEN_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DOWNLOAD</category>
            <conversions>0</conversions>
            <conversionValue>0</conversionValue>
            <allConversions>20</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>1</userRevenueValue>
            <countingType>ONE_PER_CLICK</countingType>
            <excludeFromBidding>TRUE</excludeFromBidding>
            <measurementPeriod>7</measurementPeriod>
            <appId>abc_1234</appId>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>FIRST_OPEN</appConversionType>
            <snippetId>1000661</snippetId>
            <snippetLabel>XXXXXXXXXXXXXXXXXX</snippetLabel>
            <appPostbackUrl>
              <url>&gt;http://yahoo.co.jp?advertising_id={adid}&amp;amp;lat={lat}</url>
            </appPostbackUrl>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193196</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_DOWNLOAD_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DOWNLOAD</category>
            <conversions>20</conversions>
            <conversionValue>20</conversionValue>
            <allConversions>20</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>1</userRevenueValue>
            <countingType>ONE_PER_CLICK</countingType>
            <excludeFromBidding>FALSE</excludeFromBidding>
            <measurementPeriod>90</measurementPeriod>
            <appId>abc_1234</appId>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>DOWNLOAD</appConversionType>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="WebConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193194</conversionTrackerId>
            <conversionTrackerName>WEB_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>PAGE_VIEW</category>
            <conversionTrackerType>WEB_CONVERSION</conversionTrackerType>
            <userRevenueValue>100</userRevenueValue>
            <countingType>MANY_PER_CLICK</countingType>
            <excludeFromBidding>FALSE</excludeFromBidding>
            <measurementPeriod>30</measurementPeriod>
            <snippet>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
&amp;amp;lt;script type="text/javascript"&amp;amp;gt;
    /* &amp;amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;amp;gt; */
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;amp;gt;
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;noscript&amp;amp;gt;
    &amp;amp;lt;div style="display:inline;"&amp;amp;gt;
        &amp;amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;amp;guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=true"/&amp;amp;gt;
    &amp;amp;lt;/div&amp;amp;gt;
&amp;amp;lt;/noscript&amp;amp;gt;</snippet>
            <markupLanguage>HTML</markupLanguage>
            <trackingCodeType>WEBPAGE</trackingCodeType>
            <crossDeviceConversionFlag>TRUE</crossDeviceConversionFlag>
          </conversionTracker>
        </values>
      </rval>
    </getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
コンバージョントラッカー情報を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | 操作の対象となるコンバージョントラッカー情報および操作の内容を表します。 | 

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
        <accountId>0</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="WebConversion">
          <conversionTrackerName>WebConversion</conversionTrackerName>
          <status>ENABLED</status>
          <category>DEFAULT</category>
          <conversionTrackerType>WEB_CONVERSION</conversionTrackerType>
          <markupLanguage>HTML</markupLanguage>
          <trackingCodeType>WEBPAGE</trackingCodeType>
          <crossDeviceConversionFlag>TRUE</crossDeviceConversionFlag>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
          <conversionTrackerName>AppConversion</conversionTrackerName>
          <status>ENABLED</status>
          <category>DOWNLOAD</category>
          <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
          <appId>abc_1234</appId>
          <appPlatform>ANDROID_MARKET</appPlatform>
          <appConversionType>DOWNLOAD</appConversionType>
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
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | 操作結果を含むコンバージョントラッカー情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">ConversionTracker</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutateResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <ListReturnValue.Type>AccountTrackingUrlReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193198</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DEFAULT</category>
            <conversions>0</conversions>
            <conversionValue>0</conversionValue>
            <allConversions>10</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>100</userRevenueValue>
            <countingType>MANY_PER_CLICK</countingType>
            <excludeFromBidding>TRUE</excludeFromBidding>
            <measurementPeriod>30</measurementPeriod>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>IN_APP_PURCHASE</appConversionType>
            <snippetId>1000661</snippetId>
            <snippetLabel>XXXXXXXXXXXXXXXXXX</snippetLabel>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193197</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_FIRST_OPEN_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DOWNLOAD</category>
            <conversions>0</conversions>
            <conversionValue>0</conversionValue>
            <allConversions>20</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>1</userRevenueValue>
            <countingType>ONE_PER_CLICK</countingType>
            <excludeFromBidding>TRUE</excludeFromBidding>
            <measurementPeriod>7</measurementPeriod>
            <appId>abc_1234</appId>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>FIRST_OPEN</appConversionType>
            <snippetId>1000661</snippetId>
            <snippetLabel>XXXXXXXXXXXXXXXXXX</snippetLabel>
            <appPostbackUrl>
              <url>&gt;http://yahoo.co.jp?advertising_id={adid}&amp;amp;lat={lat}</url>
            </appPostbackUrl>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193196</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_DOWNLOAD_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DOWNLOAD</category>
            <conversions>20</conversions>
            <conversionValue>20</conversionValue>
            <allConversions>20</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>1</userRevenueValue>
            <countingType>ONE_PER_CLICK</countingType>
            <excludeFromBidding>FALSE</excludeFromBidding>
            <measurementPeriod>90</measurementPeriod>
            <appId>abc_1234</appId>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>DOWNLOAD</appConversionType>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="WebConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193194</conversionTrackerId>
            <conversionTrackerName>WEB_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>PAGE_VIEW</category>
            <conversionTrackerType>WEB_CONVERSION</conversionTrackerType>
            <userRevenueValue>100</userRevenueValue>
            <countingType>MANY_PER_CLICK</countingType>
            <excludeFromBidding>FALSE</excludeFromBidding>
            <measurementPeriod>30</measurementPeriod>
            <snippet>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
&amp;amp;lt;script type="text/javascript"&amp;amp;gt;
    /* &amp;amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;amp;gt; */
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;amp;gt;
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;noscript&amp;amp;gt;
    &amp;amp;lt;div style="display:inline;"&amp;amp;gt;
        &amp;amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;amp;guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=true"/&amp;amp;gt;
    &amp;amp;lt;/div&amp;amp;gt;
&amp;amp;lt;/noscript&amp;amp;gt;</snippet>
            <markupLanguage>HTML</markupLanguage>
            <trackingCodeType>WEBPAGE</trackingCodeType>
            <crossDeviceConversionFlag>TRUE</crossDeviceConversionFlag>
          </conversionTracker>
        </values>
      </rval>
    </mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
コンバージョントラッカー情報を更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | 操作の対象となるコンバージョントラッカー設定および操作の内容を表します。 | 

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
        <accountId>0</accountId>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="WebConversion">
          <conversionTrackerId>1193194</conversionTrackerId>
          <conversionTrackerName>WebConversion_update</conversionTrackerName>
          <status>DISABLED</status>
          <category>DEFAULT</category>
          <conversionTrackerType>WEB_CONVERSION</conversionTrackerType>
          <markupLanguage>XHTML</markupLanguage>
          <trackingCodeType>CLICK_TO_CALL</trackingCodeType>
          <crossDeviceConversionFlag>TRUE</crossDeviceConversionFlag>
        </operand>
        <operand xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
          <conversionTrackerId>1193193</conversionTrackerId>
          <conversionTrackerName>AppConversion_update</conversionTrackerName>
          <status>DISABLED</status>
          <category>DOWNLOAD</category>
          <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
          <appId>abc_1234</appId>
          <appPlatform>ANDROID_MARKET</appPlatform>
          <appConversionType>DOWNLOAD</appConversionType>
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
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | 操作結果を含むコンバージョントラッカー設定に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V6">
      <service xmlns="">ConversionTracker</service>
      <remainingQuota xmlns="">-1</remainingQuota>
      <quotaUsedForThisRequest xmlns="">-1</quotaUsedForThisRequest>
      <timeTakenMillis xmlns="">0.2671</timeTakenMillis>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutateResponse xmlns="http://ss.yahooapis.jp/V6">
      <rval>
        <ListReturnValue.Type>AccountTrackingUrlReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193198</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DEFAULT</category>
            <conversions>0</conversions>
            <conversionValue>0</conversionValue>
            <allConversions>10</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>100</userRevenueValue>
            <countingType>MANY_PER_CLICK</countingType>
            <excludeFromBidding>TRUE</excludeFromBidding>
            <measurementPeriod>30</measurementPeriod>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>IN_APP_PURCHASE</appConversionType>
            <snippetId>1000661</snippetId>
            <snippetLabel>XXXXXXXXXXXXXXXXXX</snippetLabel>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193197</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_FIRST_OPEN_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DOWNLOAD</category>
            <conversions>0</conversions>
            <conversionValue>0</conversionValue>
            <allConversions>20</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>1</userRevenueValue>
            <countingType>ONE_PER_CLICK</countingType>
            <excludeFromBidding>TRUE</excludeFromBidding>
            <measurementPeriod>7</measurementPeriod>
            <appId>abc_1234</appId>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>FIRST_OPEN</appConversionType>
            <snippetId>1000661</snippetId>
            <snippetLabel>XXXXXXXXXXXXXXXXXX</snippetLabel>
            <appPostbackUrl>
              <url>&gt;http://yahoo.co.jp?advertising_id={adid}&amp;amp;lat={lat}</url>
            </appPostbackUrl>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="AppConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193196</conversionTrackerId>
            <conversionTrackerName>APP_ANDROID_DOWNLOAD_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>DOWNLOAD</category>
            <conversions>20</conversions>
            <conversionValue>20</conversionValue>
            <allConversions>20</allConversions>
            <conversionTrackerType>APP_CONVERSION</conversionTrackerType>
            <userRevenueValue>1</userRevenueValue>
            <countingType>ONE_PER_CLICK</countingType>
            <excludeFromBidding>FALSE</excludeFromBidding>
            <measurementPeriod>90</measurementPeriod>
            <appId>abc_1234</appId>
            <appPlatform>ANDROID_MARKET</appPlatform>
            <appConversionType>DOWNLOAD</appConversionType>
          </conversionTracker>
        </values>
        <values>
          <operationSucceeded>true</operationSucceeded>
          <conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="WebConversion">
            <accountId>1111</accountId>
            <conversionTrackerId>1193194</conversionTrackerId>
            <conversionTrackerName>WEB_コンバージョントラッカー</conversionTrackerName>
            <status>ENABLED</status>
            <category>PAGE_VIEW</category>
            <conversionTrackerType>WEB_CONVERSION</conversionTrackerType>
            <userRevenueValue>100</userRevenueValue>
            <countingType>MANY_PER_CLICK</countingType>
            <excludeFromBidding>FALSE</excludeFromBidding>
            <measurementPeriod>30</measurementPeriod>
            <snippet>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
&amp;amp;lt;script type="text/javascript"&amp;amp;gt;
    /* &amp;amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;amp;gt; */
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;amp;gt;
&amp;amp;lt;/script&amp;amp;gt;
&amp;amp;lt;noscript&amp;amp;gt;
    &amp;amp;lt;div style="display:inline;"&amp;amp;gt;
        &amp;amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;amp;guid=ON&amp;amp;amp;script=0&amp;amp;amp;disvt=true"/&amp;amp;gt;
    &amp;amp;lt;/div&amp;amp;gt;
&amp;amp;lt;/noscript&amp;amp;gt;</snippet>
            <markupLanguage>HTML</markupLanguage>
            <trackingCodeType>WEBPAGE</trackingCodeType>
            <crossDeviceConversionFlag>TRUE</crossDeviceConversionFlag>
          </conversionTracker>
        </values>
      </rval>
    </mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
