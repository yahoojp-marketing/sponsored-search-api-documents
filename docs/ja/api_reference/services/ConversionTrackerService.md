# ConversionTrackerService
ConversionTrackerServiceでは、コンバージョントラッカー情報の取得および追加・更新を行います。<br>
コンバージョントラッカー情報とは、コンバージョン測定タグおよびタグごとのパフォーマンスデータを表します。<br>
本サービスを利用することで、スポンサードサーチで掲載されている広告からのコンバージョン数（商品の購入や会員登録、資料請求などサイト上で何らかの成約に至った件数）を取得することができ、広告がどの程度成果を上げているかなどを確認できます。<br>
コンバージョンタグは広告管理ツールとAPIで共有しています。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/ConversionTrackerService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/ConversionTrackerService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/ConversionTracker
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

#### 操作
ConversionTrackerServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)

#### オブジェクト
[ConversionTracker](../data/ConversionTracker)

## get
コンバージョントラッカー情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [ConversionTrackerSelector](../data/ConversionTracker/ConversionTrackerSelector.md) | 操作の対象とするコンバージョントラッカー情報の設定です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201805">
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
| rval | [ConversionTrackerPage](../data/ConversionTracker/ConversionTrackerPage.md) | 取得されるコンバージョントラッカー情報に関するエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1523506333098</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/ConversionTracker">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <ns2:totalConversions>20</ns2:totalConversions>
        <ns2:totalAllConversions>50</ns2:totalAllConversions>
        <ns2:totalConversionValue>20</ns2:totalConversionValue>
        <ns2:totalAllConversionValue>50</ns2:totalAllConversionValue>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193198</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DEFAULT</ns2:category>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:allConversions>10</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:countingType>MANY_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>IN_APP_PURCHASE</ns2:appConversionType>
            <ns2:snippetId>1000661</ns2:snippetId>
            <ns2:snippetLabel>XXXXXXXXXXXXXXXXXX</ns2:snippetLabel>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193197</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_FIRST_OPEN_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>7</ns2:measurementPeriod>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
            <ns2:snippetId>1000661</ns2:snippetId>
            <ns2:snippetLabel>XXXXXXXXXXXXXXXXXX</ns2:snippetLabel>
            <ns2:appPostbackUrl>
              <ns2:url>&gt;http://yahoo.co.jp?advertising_id={adid}&amp;amp;lat={lat}</ns2:url>
            </ns2:appPostbackUrl>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193196</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_DOWNLOAD_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>FALSE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>90</ns2:measurementPeriod>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>DOWNLOAD</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:WebConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193194</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>WEB_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>PAGE_VIEW</ns2:category>
            <ns2:conversionTrackerType>WEB_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:countingType>MANY_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>FALSE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:snippet>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
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
&amp;amp;lt;/noscript&amp;amp;gt;</ns2:snippet>
            <ns2:markupLanguage>HTML</ns2:markupLanguage>
            <ns2:trackingCodeType>WEBPAGE</ns2:trackingCodeType>
            <ns2:crossDeviceConversionFlag>TRUE</ns2:crossDeviceConversionFlag>
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
コンバージョントラッカー情報を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTracker/ConversionTrackerOperation.md) | 操作の対象となるコンバージョントラッカー情報および操作の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker">
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
| rval | [ConversionTrackerReturnValue](../data/ConversionTracker/ConversionTrackerReturnValue.md) | 操作結果を含むコンバージョントラッカー情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1523506333125</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/ConversionTracker">
      <ns2:rval>
        <ListReturnValue.Type>AccountTrackingUrlReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193198</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DEFAULT</ns2:category>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:allConversions>10</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:countingType>MANY_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>IN_APP_PURCHASE</ns2:appConversionType>
            <ns2:snippetId>1000661</ns2:snippetId>
            <ns2:snippetLabel>XXXXXXXXXXXXXXXXXX</ns2:snippetLabel>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193197</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_FIRST_OPEN_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>7</ns2:measurementPeriod>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
            <ns2:snippetId>1000661</ns2:snippetId>
            <ns2:snippetLabel>XXXXXXXXXXXXXXXXXX</ns2:snippetLabel>
            <ns2:appPostbackUrl>
              <ns2:url>&gt;http://yahoo.co.jp?advertising_id={adid}&amp;amp;lat={lat}</ns2:url>
            </ns2:appPostbackUrl>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193196</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_DOWNLOAD_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>FALSE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>90</ns2:measurementPeriod>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>DOWNLOAD</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:WebConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193194</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>WEB_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>PAGE_VIEW</ns2:category>
            <ns2:conversionTrackerType>WEB_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:countingType>MANY_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>FALSE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:snippet>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
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
&amp;amp;lt;/noscript&amp;amp;gt;</ns2:snippet>
            <ns2:markupLanguage>HTML</ns2:markupLanguage>
            <ns2:trackingCodeType>WEBPAGE</ns2:trackingCodeType>
            <ns2:crossDeviceConversionFlag>TRUE</ns2:crossDeviceConversionFlag>
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
コンバージョントラッカー情報を更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 |
|---|---|---|---|
| operations | ○ | [ConversionTrackerOperation](../data/ConversionTracker/ConversionTrackerOperation.md) | 操作の対象となるコンバージョントラッカー設定および操作の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker">
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
| rval | [ConversionTrackerReturnValue](../data/ConversionTracker/ConversionTrackerReturnValue.md) | 操作結果を含むコンバージョントラッカー設定に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1523506333154</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/ConversionTracker">
      <ns2:rval>
        <ListReturnValue.Type>AccountTrackingUrlReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193198</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DEFAULT</ns2:category>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:allConversions>10</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:countingType>MANY_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>IN_APP_PURCHASE</ns2:appConversionType>
            <ns2:snippetId>1000661</ns2:snippetId>
            <ns2:snippetLabel>XXXXXXXXXXXXXXXXXX</ns2:snippetLabel>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193197</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_FIRST_OPEN_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:conversions>0</ns2:conversions>
            <ns2:conversionValue>0</ns2:conversionValue>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>TRUE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>7</ns2:measurementPeriod>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>FIRST_OPEN</ns2:appConversionType>
            <ns2:snippetId>1000661</ns2:snippetId>
            <ns2:snippetLabel>XXXXXXXXXXXXXXXXXX</ns2:snippetLabel>
            <ns2:appPostbackUrl>
              <ns2:url>&gt;http://yahoo.co.jp?advertising_id={adid}&amp;amp;lat={lat}</ns2:url>
            </ns2:appPostbackUrl>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AppConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193196</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>APP_ANDROID_DOWNLOAD_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>DOWNLOAD</ns2:category>
            <ns2:conversions>20</ns2:conversions>
            <ns2:conversionValue>20</ns2:conversionValue>
            <ns2:allConversions>20</ns2:allConversions>
            <ns2:conversionTrackerType>APP_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>1</ns2:userRevenueValue>
            <ns2:countingType>ONE_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>FALSE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>90</ns2:measurementPeriod>
            <ns2:appId>abc_1234</ns2:appId>
            <ns2:appPlatform>ANDROID_MARKET</ns2:appPlatform>
            <ns2:appConversionType>DOWNLOAD</ns2:appConversionType>
          </ns2:conversionTracker>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:conversionTracker xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:WebConversion">
            <ns2:accountId>1111</ns2:accountId>
            <ns2:conversionTrackerId>1193194</ns2:conversionTrackerId>
            <ns2:conversionTrackerName>WEB_CONVERSION_TRACKER</ns2:conversionTrackerName>
            <ns2:status>ENABLED</ns2:status>
            <ns2:category>PAGE_VIEW</ns2:category>
            <ns2:conversionTrackerType>WEB_CONVERSION</ns2:conversionTrackerType>
            <ns2:userRevenueValue>100</ns2:userRevenueValue>
            <ns2:countingType>MANY_PER_CLICK</ns2:countingType>
            <ns2:excludeFromBidding>FALSE</ns2:excludeFromBidding>
            <ns2:measurementPeriod>30</ns2:measurementPeriod>
            <ns2:snippet>&amp;amp;lt;!-- Yahoo Code for your Conversion Page --&amp;amp;gt;
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
&amp;amp;lt;/noscript&amp;amp;gt;</ns2:snippet>
            <ns2:markupLanguage>HTML</ns2:markupLanguage>
            <ns2:trackingCodeType>WEBPAGE</ns2:trackingCodeType>
            <ns2:crossDeviceConversionFlag>TRUE</ns2:crossDeviceConversionFlag>
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
