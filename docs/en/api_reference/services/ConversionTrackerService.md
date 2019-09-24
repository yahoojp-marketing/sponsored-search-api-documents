# ConversionTrackerService
ConversionTrackerService is to get, add, and update ConversionTracker information. <br>
Number of conversions and performance of Ads in Sponsored Search can be obtained.<br>
Conversion tag will be shared both in Campaign Management Tool and API.<br>
*ConversionTrackerInformation means Conversion Tag and performance data per tag. This service enables you to confirm the effect of your advertising campaign by tracking conversions on Sponsored Search ad such as purchasing products, member signup, document request.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/ConversionTrackerService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/ConversionTrackerService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201909/ConversionTracker
#### Service Overview
Get, add, update ConversionTracker informations.
#### Notes
ConversionTrackerService has following restrictions.<br>
・You can acquire up to 1,000 conversion tags in three kinds such as Web Page , Click to Call , App Download.<br>
・Conversion Tag will not be removed. Please create a new tag or update the created Conversion Tag. <br>
・Conversion is measured based on cookie.<br>
・If you add/edit conversion tag after November 16, 2016, you can set the counting period between 7 to 90 days after clicked the ad.<br>For Mobile App Download ad, the counting period is fixed as 30days after clicked.
・For the measurement of the phone call conversion, you must setting the "conversion tracking tag" and "on-click event tag" on your site.<br>The installation method of "on-click event tag", please check Sponsored Search help pages.<br>
https://support-marketing.yahoo.co.jp/promotionalads/ss/articledetail?lan=en&aid=363<br>

Please also refer Sponsored Search help pages for Conversion Analytics:<br>
https://support-marketing.yahoo.co.jp/promotionalads/middlecategory?lan=en&cid=636

#### Operation
Describes the operation which provides at ConversionTrackerService.
+ [get](#get)
+ [mutate(ADD)](#mutate-add)
+ [mutate(SET)](#mutate-set)

#### Object
[ConversionTracker](../data/ConversionTracker)

## get
Describes the operation which provide at ConversionTrackerService

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [ConversionTrackerSelector](../data/ConversionTracker/ConversionTrackerSelector.md) | Operation elements for ConversionTracker informations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201909">
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

### Response
Response Fields for normal cases.

| Field | Data Type | Description |
|---|---|---|
| rval | [ConversionTrackerPage](../data/ConversionTracker/ConversionTrackerPage.md) | Page of lists of the requested ConversionTracker informations. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1547792970989</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/ConversionTracker">
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
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Add ConversionTracker informations.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [ConversionTrackerOperation](../data/ConversionTracker/ConversionTrackerOperation.md) | Operation elements for ConversionTracker informations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker">
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

### Response
Response Fields for normal cases.

| Field | Data Type | Description |
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTracker/ConversionTrackerReturnValue.md) | Container for ConversionTracker information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1547792971026</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/ConversionTracker">
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
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
Update ConversionTracker informations.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [ConversionTrackerOperation](../data/ConversionTracker/ConversionTrackerOperation.md) | Operation elements for ConversionTracker informations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker">
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

### Response
Response Fields for normal cases.

| Field | Data Type | Description |
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTracker/ConversionTrackerReturnValue.md) | Container for ConversionTracker information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/ConversionTracker" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>ConversionTracker</ns2:service>
      <ns2:requestTime>1547792971069</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/ConversionTracker">
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
          </ns2:conversionTracker>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
