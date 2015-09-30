# ConversionTrackerService
ConversionTrackerService is to get, add, and update ConversionTracker information. <br>
Number of conversions and performance of Ads in Sponsored Search can be obtained.<br>
Conversion tag will be shared both in Campaign Management Tool and API.<br>
*ConversionTrackerInformation means Conversion Tag and performance data per tag.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.2/ConversionTrackerService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.2/ConversionTrackerService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Get, add, update ConversionTracker informations.
#### Notes
ConversionTrackerService has following restrictions.<br>
・You can acquire up to 1000 conversion tags in three kinds such as Web Page , Click to Call , App Download.<br>
・Conversion Tag will not be removed. Please use it by updating the created Conversion Tag. <br>
・Conversion is measured based on cookie.<br>
・Conversion is counted within 30 days after Ad is clicked.<br>
・For the measurement of the phone call conversion, you must setting the "conversion measurement tag" and "on-click event tag" on your site.<br>
　The installation method of "on-click event tag", please check the help pages of Yahoo! promotional advertising.<br>
<br>
Please refer “help” page in Yahoo! JAPAN Promotional Ads for Conversion Analytics:<br>
http://help.marketing.yahoo.co.jp/en/?p=367

## get
### Request
Describes the operation which provide at ConversionTrackerService

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [ConversionTrackerSelector](../data/ConversionTrackerSelector.md) | Operation elements for ConversionTracker informations. | 

##### Request Sample
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
### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ConversionTrackerPage](../data/ConversionTrackerPage.md) | Page of lists of the requested ConversionTracker informations. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
## mutate (ADD)
### Request
Add ConversionTracker informations.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | Operation elements for ConversionTracker informations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:conversionTrackerName>WEB_コンバージョントラッカー</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>PAGE_VIEW</ns1:category>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
               <ns1:userRevenueValue>100</ns1:userRevenueValue>
               <ns1:markupLanguage>HTML</ns1:markupLanguage>
               <ns1:httpProtocol>HTTP</ns1:httpProtocol>
               <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
            </ns1:operand>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:conversionTrackerName>CALL_コンバージョントラッカー</ns1:conversionTrackerName>
               <ns1:status>DISABLED</ns1:status>
               <ns1:category>DEFAULT</ns1:category>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
               <ns1:userRevenueValue>200</ns1:userRevenueValue>
               <ns1:markupLanguage>HTML</ns1:markupLanguage>
               <ns1:httpProtocol>HTTP</ns1:httpProtocol>
               <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
            </ns1:operand>
            <ns1:operand xsi:type="ns1:AppConversion">
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:conversionTrackerName>APP_コンバージョントラッカー</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DOWNLOAD</ns1:category>
               <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
               <ns1:userRevenueValue>100</ns1:userRevenueValue>
               <ns1:appId>abc_1234</ns1:appId>
               <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
               <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | Container for ConversionTracker information including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ConversionTrackerService</ns1:service>
      <ns1:remainingQuota>4967</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.1225</ns1:timeTakenMillis>
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
            <ns1:conversionTrackerId>1000002</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>WEB_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PURCHASE</ns1:category>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
             <ns1:userRevenueValue>1500</ns1:userRevenueValue>
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
            <ns1:conversionTrackerName>CALL_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PURCHASE</ns1:category>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>1500</ns1:userRevenueValue>
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
            <ns1:conversionTrackerName>APP_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>DOWNLOAD</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:userRevenueValue>100</ns1:userRevenueValue>
            <ns1:appId>abc_1234</ns1:appId>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
          </ns1:conversionTracker>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
### Request
Update ConversionTracker informations.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | Operation elements for ConversionTracker informations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:conversionTrackerId>00000003</ns1:conversionTrackerId>
               <ns1:conversionTrackerName>WEB_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>PAGE_VIEW</ns1:category>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
               <ns1:userRevenueValue>100</ns1:userRevenueValue>
               <ns1:markupLanguage>HTML</ns1:markupLanguage>
               <ns1:httpProtocol>HTTP</ns1:httpProtocol>
               <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
            </ns1:operand>
            <ns1:operand xsi:type="ns1:WebConversion">
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:conversionTrackerId>00000003</ns1:conversionTrackerId>
               <ns1:conversionTrackerName>CALL_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
               <ns1:status>DISABLED</ns1:status>
               <ns1:category>DEFAULT</ns1:category>
               <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
               <ns1:userRevenueValue>200</ns1:userRevenueValue>
               <ns1:markupLanguage>HTML</ns1:markupLanguage>
               <ns1:httpProtocol>HTTP</ns1:httpProtocol>
               <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
            </ns1:operand>
            <ns1:operand xsi:type="ns1:AppConversion">
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:conversionTrackerId>00000005</ns1:conversionTrackerId>
               <ns1:conversionTrackerName>APP_コンバージョントラッカーEDIT</ns1:conversionTrackerName>
               <ns1:status>ENABLED</ns1:status>
               <ns1:category>DOWNLOAD</ns1:category>
               <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
               <ns1:userRevenueValue>200</ns1:userRevenueValue>
               <ns1:appId>abc_1234</ns1:appId>
               <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
               <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | Container for ConversionTracker information including operation results. |

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ConversionTrackerService</ns1:service>
      <ns1:remainingQuota>4967</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.1225</ns1:timeTakenMillis>
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
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:conversionTrackerId>00000003</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>WEB_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PURCHASE</ns1:category>
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
            <ns1:userRevenueValue>1500</ns1:userRevenueValue>
            <ns1:trackingCodeType>WEBPAGE</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:WebConversion">
            <ns1:accountId>2000003390</ns1:accountId>
            <ns1:conversionTrackerId>1000003</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>CALL_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:category>PURCHASE</ns1:category>
            <ns1:conversionTrackerType>WEB_CONVERSION</ns1:conversionTrackerType>
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
            <ns1:userRevenueValue>1500</ns1:userRevenueValue>
            <ns1:trackingCodeType>CLICK_TO_CALL</ns1:trackingCodeType>
          </ns1:conversionTracker>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:conversionTracker xsi:type="ns1:AppConversion">
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:conversionTrackerId>00000005</ns1:conversionTrackerId>
            <ns1:conversionTrackerName>APP_コンバージョントラッカー</ns1:conversionTrackerName>
            <ns1:status>ENABLED</ns1:status>
            <ns1:userRevenueValue>200</ns1:userRevenueValue>
            <ns1:category>DEFAULT</ns1:category>
            <ns1:conversionTrackerType>APP_CONVERSION</ns1:conversionTrackerType>
            <ns1:appId>abc_1234</ns1:appId>
            <ns1:appPlatform>ANDROID_MARKET</ns1:appPlatform>
            <ns1:appConversionType>DOWNLOAD</ns1:appConversionType>
          </ns1:conversionTracker>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
