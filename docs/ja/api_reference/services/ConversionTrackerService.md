# ConversionTrackerService
ConversionTrackerServiceでは、コンバージョントラッカー情報の取得および追加・更新を行います。<br>
コンバージョントラッカー情報とは、コンバージョン測定タグおよびタグごとのパフォーマンスデータを表します。<br>
本サービスを利用することで、スポンサードサーチで掲載されている広告からのコンバージョン数（商品の購入や会員登録、資料請求などサイト上で何らかの成約に至った件数）を取得することができ、広告がどの程度成果を上げているかなどを確認できます。<br>
コンバージョンタグは広告管理ツールとAPIで共有しています。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/ConversionTrackerService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/ConversionTrackerService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### サービス概要
コンバージョントラッカー情報の取得およびコンバージョントラッカー情報の追加・更新を行います。
#### 注意事項
ConversionTrackerServiceには以下の注意事項があります。<br>
・コンバージョン測定は、アカウントごとにウェブページ・電話発信・アプリダウンロードの3種類あわせて1000件まで設定可能です。<br>
・一度作成したコンバージョンタグは削除できません。作成したコンバージョンタグを変更して、ご利用ください。<br>
・コンバージョン測定は、クッキー情報を元に実施します。<br>
・広告がクリックされてから30日以内に発生したコンバージョンをカウントします。<br>
・電話発信コンバージョンの測定のためには、お客様のサイト内に「コンバージョン測定タグ」と<br>　「オンクリックイベントタグ」を設置する必要があります。<br>
　「オンクリックイベントタグ」の設置方法は、Yahoo!プロモーション広告のヘルプページをご確認ください。<br>
<br>
その他、コンバージョン測定については、Yahoo!プロモーション広告のヘルプを参照してください。<br>
http://help.marketing.yahoo.co.jp/ja/?p=1161<br>
## get
ConversionTrackerServiceで提供される操作を説明します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [ConversionTrackerSelector](../data/ConversionTrackerSelector.md) | 操作の対象とするコンバージョントラッカー情報の設定です。 | 
##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>00000001</ns1:accountId>
        <ns1:conversionTrackerIds>11</ns1:conversionTrackerIds>
        <ns1:conversionTrackerIds>13</ns1:conversionTrackerIds>
        <ns1:statuses>ENABLED</ns1:statuses>
        <ns1:statuses>DISABLED</ns1:statuses>
        <ns1:categories>DEFAULT</ns1:categories>
        <ns1:categories>PAGE_VIEW</ns1:categories>
        <ns1:categories>PURCHASE</ns1:categories>
        <ns1:categories>SIGNUP</ns1:categories>
        <ns1:categories>LEAD</ns1:categories>
        <ns1:conversionTrackerTypes>WEB_CONVERSION</ns1:conversionTrackerTypes>
        <ns1:conversionTrackerTypes>APP_CONVERSION</ns1:conversionTrackerTypes>
        <ns1:trackingCodeTypes>WEBPAGE</ns1:trackingCodeTypes>
        <ns1:trackingCodeTypes>CLICK_TO_CALL</ns1:trackingCodeTypes>
        <ns1:dateRange>
          <ns1:startDate>19700101</ns1:startDate>
          <ns1:endDate>20371231</ns1:endDate>
        </ns1:dateRange>
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>20</ns1:numberResults>
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
| rval | [ConversionTrackerPage](../data/ConversionTrackerPage.md) | 取得されるコンバージョントラッカー情報に関するエントリーです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5" 
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ConversionTrackerService</ns1:service>
      <ns1:remainingQuota>4967</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.1225</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
      <ns1:totalNumEntries>3</ns1:totalNumEntries>
      <ns1:Page.Type>ConversionTrackerPage</ns1:Page.Type>
        <ns1:totalNumConvertedClicks>115</ns1:totalNumConvertedClicks>
        <ns1:totalNumConversionEvents>24</ns1:totalNumConversionEvents>
        <ns1:totalConversionValue>3900</ns1:totalConversionValue>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:WebConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1000001</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>コンバージョントラッカー名</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PURCHASE</ns1:category>
            <ns1:numConversionEvents>2</ns1:numConversionEvents>
            <ns1:conversionValue>300</ns1:conversionValue>
            <ns1:mostRecentConversionDate>20131231</ns1:mostRecentConversionDate>
            <ns1:numConvertedClicks>51</ns1:numConvertedClicks>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            <ns1:snippet>&lt;!-- Yahoo Code for your Conversion Page --&gt;
&lt;script type="text/javascript"&gt;
/* &lt;![CDATA[ */
var yahoo_conversion_id = 1000661;
var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
var yahoo_conversion_value = 100;
/* ]]&gt; */
&lt;/script&gt;
&lt;script type="text/javascript" src="http://XXXXXXXXX/XXXXXX/XXXXXXX/XXXX/XX/conversion.js"&gt;
&lt;/script&gt;
&lt;noscript&gt;
&lt;div style="display:inline;"&gt;
&lt;img height="1" width="1" style="border-style:none;" alt="" src="http://XXXXXXXXXXXXXXX/pagead/conversion/1000661/?value=100&amp;label=XXXXXXXXXXXXXXXXXX&amp;guid=ON&amp;script=0&amp;disvt=true"/&gt;
&lt;/div&gt;
&lt;/noscript&gt;</ns1:snippet>
            <ns1:markupLanguage>HTML</ns1:markupLanguage>
            <ns1:httpProtocol>HTTP</ns1:httpProtocol>
            <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:WebConversion">
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:conversionTrackerId>00000002</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>コンバージョントラッカー名</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PURCHASE</ns1:category>
            <ns1:numConversionEvents>1</ns1:numConversionEvents>
            <ns1:conversionValue>300</ns1:conversionValue>
            <ns1:mostRecentConversionDate>20131231</ns1:mostRecentConversionDate>
            <ns1:numConvertedClicks>11</ns1:numConvertedClicks>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>300</ns1:userRevenueValue>
            <ns1:snippet>
&lt;!-- Yahoo Code for your Conversion Page
In your html page, add the snippet and call
yahoo_report_conversion when someone clicks on the
phone number link or button. --&gt;
&lt;script type="text/javascript"&gt;
  /* &lt;![CDATA[ */
  yahoo_snippet_vars = function() {
    var w = window;
    w.yahoo_conversion_id = 1000661;
    w.yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    w.yahoo_conversion_value = 100;
    w.yahoo_remarketing_only = false;
  }
  // IF YOU CHANGE THE CODE BELOW, THIS CONVERSION TAG MAY NOT WORK.
  yahoo_report_conversion = function(url) {
    yahoo_snippet_vars();
    window.yahoo_conversion_format = "3";
    window.yahoo_is_call = true;
    var opt = new Object();
    opt.onload_callback = function() {
      if (typeof(url) != 'undefined') {
        window.location = url;
      }
    }
    var conv_handler = window['yahoo_trackConversion'];
    if (typeof(conv_handler) == 'function') {
      conv_handler(opt);
    }
  }
/* ]]&gt; */
&lt;/script&gt;
&lt;script type="text/javascript"
  src="http://XXXXXXXXX/XXXXXX/XXXXXXX/XXXX/XX/conversion_async.js"&gt;
&lt;/script&gt;</ns1:snippet>
            <ns1:markupLanguage>HTML</ns1:markupLanguage>
            <ns1:httpProtocol>HTTP</ns1:httpProtocol>
            <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:conversionTrackerId>00000005</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>コンバージョントラッカー名</ns1:conversionTrackerName>
            <ns1:status>DISABLED</ns1:status>
            <ns1:category>DOWNLOAD</ns1:category>
            <ns1:numConversionEvents>10</ns1:numConversionEvents>
            <ns1:conversionValue>300</ns1:conversionValue>
            <ns1:mostRecentConversionDate>20131231</ns1:mostRecentConversionDate>
            <ns1:numConvertedClicks>54</ns1:numConvertedClicks>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appId>abc_123</ns1:appId>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
          </ns1:conversionTracker>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>9999-9999-9999-9999</ns1:license>
      <ns1:apiAccountId>9999-9999-9999-9999</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>2000003390</ns1:accountId>
        <ns1:operand xsi:type="ns1:WebConversion">
          <ns1:conversionTrackerName>WEB_コンバージョントラッカー</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>PAGE_VIEW</ns1:category>
          <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
          <ns1:markupLanguage>HTML</ns1:markupLanguage>
          <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:WebConversion">
          <ns1:conversionTrackerName>CALL_コンバージョントラッカー</ns1:conversionTrackerName>
          <ns1:status>DISABLED</ns1:status>
          <ns1:category>DEFAULT</ns1:category>
          <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>200</ns1:userRevenueValue>
          <ns1:markupLanguage>HTML</ns1:markupLanguage>
          <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:AppConversion">
          <ns1:conversionTrackerName>APP_ANDROID_DOWNLOAD_コンバージョントラッカー</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>DOWNLOAD</ns1:category>
          <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
          <ns1:appId>abc_1234</ns1:appId>
          <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
          <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:AppConversion">
          <ns1:conversionTrackerName>APP_ANDROID_FIRST_OPEN_コンバージョントラッカー</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>DOWNLOAD</ns1:category>
          <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
          <ns1:appId>abc_1234</ns1:appId>
          <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
          <ns1:appConversionType>FIRST_OPEN</ns1:appConversionType>
          <ns1:appPostbackUrl>
            <ns1:url>http://yahoo.co.jp?advertising_id={adid}&amp;lat={lat}</ns1:url>
          </ns1:appPostbackUrl>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:AppConversion">
          <ns1:conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_コンバージョントラッカー</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>DEFAULT</ns1:category>
          <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
          <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
          <ns1:appConversionType>IN_APP_PURCHASE</ns1:appConversionType>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ConversionTrackerService</ns1:service>
      <ns1:remainingQuota>6547</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>2.4381</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>ConversionTrackerReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:WebConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193194</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>WEB_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PAGE_VIEW</ns1:category>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:markupLanguage>HTML</ns1:markupLanguage>
            <ns1:httpProtocol>HTTP</ns1:httpProtocol>
            <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:WebConversion">
            <ns1:accountId>20741</ns1:accountId>
            <ns1:conversionTrackerId>1193195</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>CALL_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>DISABLED</ns1:status>
            <ns1:category>DEFAULT</ns1:category>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>200</ns1:userRevenueValue>
            <ns1:markupLanguage>HTML</ns1:markupLanguage>
            <ns1:httpProtocol>HTTP</ns1:httpProtocol>
            <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193196</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>APP_ANDROID_DOWNLOAD_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>DOWNLOAD</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appId>abc_1234</ns1:appId>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
            <ns1:appPostbackUrl />
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>20741</ns1:accountId>
            <ns1:conversionTrackerId>1193197</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>APP_ANDROID_FIRST_OPEN_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>DOWNLOAD</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appId>abc_1234</ns1:appId>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>FIRST_OPEN</ns1:appConversionType>
            <ns1:appPostbackUrl>
              <ns1:url>http://yahoo.co.jp?advertising_id={adid}&amp;lat={lat}</ns1:url>
            </ns1:appPostbackUrl>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193198</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>DEFAULT</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>IN_APP_PURCHASE</ns1:appConversionType>
            <ns1:appPostbackUrl />
          </ns1:conversionTracker>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>9999-9999-9999-9999</ns1:license>
      <ns1:apiAccountId>9999-9999-9999-9999</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>SET</ns1:operator>
        <ns1:accountId>2000003390</ns1:accountId>
        <ns1:operand xsi:type="ns1:WebConversion">
          <ns1:conversionTrackerId>1193194</ns1:conversionTrackerId>
          <ns1:conversionTrackerName>WEB_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>PAGE_VIEW</ns1:category>
          <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
          <ns1:markupLanguage>HTML</ns1:markupLanguage>
          <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:WebConversion">
          <ns1:conversionTrackerId>1193195</ns1:conversionTrackerId>
          <ns1:conversionTrackerName>CALL_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
          <ns1:status>DISABLED</ns1:status>
          <ns1:category>DEFAULT</ns1:category>
          <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>200</ns1:userRevenueValue>
          <ns1:markupLanguage>HTML</ns1:markupLanguage>
          <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:AppConversion">
          <ns1:conversionTrackerId>1193196</ns1:conversionTrackerId>
          <ns1:conversionTrackerName>APP_ANDROID_DOWNLOAD_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>DOWNLOAD</ns1:category>
          <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
          <ns1:appId>abc_1234</ns1:appId>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:AppConversion">
          <ns1:conversionTrackerId>1193197</ns1:conversionTrackerId>
          <ns1:conversionTrackerName>APP_ANDROID_FIRST_OPEN_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>DOWNLOAD</ns1:category>
          <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
          <ns1:appId>abc_1234</ns1:appId>
          <ns1:appPostbackUrl>
            <ns1:clearFlag>TRUE</ns1:clearFlag>
          </ns1:appPostbackUrl>
        </ns1:operand>
        <ns1:operand xsi:type="ns1:AppConversion">
          <ns1:conversionTrackerId>1193198</ns1:conversionTrackerId>
          <ns1:conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
          <ns1:status>ENABLED</ns1:status>
          <ns1:category>PURCHASE</ns1:category>
          <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
          <ns1:userRevenueValue>100</ns1:userRevenueValue>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ConversionTrackerService</ns1:service>
      <ns1:remainingQuota>6529</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>5</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>3.4503</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>ConversionTrackerReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:WebConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193194</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>WEB_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PAGE_VIEW</ns1:category>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:snippet>&amp;lt;!-- Yahoo Code for your Conversion Page --&amp;gt;
&amp;lt;script type="text/javascript"&amp;gt;
    /* &amp;lt;![CDATA[ */
    var yahoo_conversion_id = 1000661;
    var yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
    var yahoo_conversion_value = 100;
    /* ]]&amp;gt; */
&amp;lt;/script&amp;gt;
&amp;lt;script type="text/javascript" src="//s.yimg.jp/images/listing/tool/cv/conversion.js"&amp;gt;
&amp;lt;/script&amp;gt;
&amp;lt;noscript&amp;gt;
    &amp;lt;div style="display:inline;"&amp;gt;
        &amp;lt;img height="1" width="1" style="border-style:none;" alt="" src="//b91.yahoo.co.jp/pagead/conversion/1000661/?value=100&amp;amp;label=XXXXXXXXXXXXXXXXXX&amp;amp;guid=ON&amp;amp;script=0&amp;amp;disvt=true"/&amp;gt;
    &amp;lt;/div&amp;gt;
&amp;lt;/noscript&amp;gt;</ns1:snippet>
            <ns1:markupLanguage>HTML</ns1:markupLanguage>
            <ns1:httpProtocol>HTTP</ns1:httpProtocol>
            <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:WebConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193195</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>CALL_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
            <ns1:status>DISABLED</ns1:status>
            <ns1:category>DEFAULT</ns1:category>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>200</ns1:userRevenueValue>
            <ns1:snippet>&amp;lt;!-- Yahoo Code for your Conversion Page In your html page, add the snippet and call
yahoo_report_conversion when someone clicks on the phone number link or button. --&amp;gt;
&amp;lt;script type="text/javascript"&amp;gt;
    /* &amp;lt;![CDATA[ */
    yahoo_snippet_vars = function() {
        var w = window;
        w.yahoo_conversion_id = 1000661;
        w.yahoo_conversion_label = "XXXXXXXXXXXXXXXXXX";
        w.yahoo_conversion_value = 200;
        w.yahoo_remarketing_only = false;
    }
    // IF YOU CHANGE THE CODE BELOW, THIS CONVERSION TAG MAY NOT WORK.
    yahoo_report_conversion = function(url) {
        yahoo_snippet_vars();
        window.yahoo_conversion_format = "3";
        window.yahoo_is_call = true;
        var opt = new Object();
        opt.onload_callback = function() {
            if (typeof(url) != 'undefined') {
                window.location = url;
            }
        }
        var conv_handler = window['yahoo_trackConversion'];
        if (typeof(conv_handler) == 'function') {
            conv_handler(opt);
        }
    }
    /* ]]&amp;gt; */
&amp;lt;/script&amp;gt;
&amp;lt;script type="text/javascript"
        src="//s.yimg.jp/images/listing/tool/cv/conversion_async.js"&amp;gt;
&amp;lt;/script&amp;gt;</ns1:snippet>
            <ns1:markupLanguage>HTML</ns1:markupLanguage>
            <ns1:httpProtocol>HTTP</ns1:httpProtocol>
            <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193196</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>APP_ANDROID_DOWNLOAD_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>DOWNLOAD</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appId>abc_1234</ns1:appId>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
            <ns1:appPostbackUrl />
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193197</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>APP_ANDROID_FIRST_OPEN_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>DOWNLOAD</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appId>abc_1234</ns1:appId>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>FIRST_OPEN</ns1:appConversionType>
            <ns1:snippetId>1000661</ns1:snippetId>
            <ns1:snippetLabel>XXXXXXXXXXXXXXXXXX</ns1:snippetLabel>
            <ns1:appPostbackUrl />
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1193198</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PURCHASE</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>IN_APP_PURCHASE</ns1:appConversionType>
            <ns1:snippetId>1000661</ns1:snippetId>
            <ns1:snippetLabel>XXXXXXXXXXXXXXXXXX</ns1:snippetLabel>
            <ns1:appPostbackUrl />
          </ns1:conversionTracker>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
