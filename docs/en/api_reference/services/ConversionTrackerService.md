# ConversionTrackerService
ConversionTrackerService is to get, add, and update ConversionTracker information. <br>
Number of conversions and performance of Ads in Sponsored Search can be obtained.<br>
Conversion tag will be shared both in Campaign Management Tool and API.<br>
*ConversionTrackerInformation means Conversion Tag and performance data per tag. This service enables you to confirm the effect of your advertising campaign by tracking conversions on Sponsored Search ad such as purchasing products, member signup, document request.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/ConversionTrackerService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/ConversionTrackerService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Service Overview
Get, add, update ConversionTracker informations.
#### Notes
ConversionTrackerService has following restrictions.<br>
・You can acquire up to 1,000 conversion tags in three kinds such as Web Page , Click to Call , App Download.<br>
・Conversion Tag will not be removed. Please create a new tag or update the created Conversion Tag. <br>
・Conversion is measured based on cookie.<br>
・If you add/edit conversion tag after November 16, 2016, you can set the counting period between 7 to 90 days after clicked the ad.<br>For Mobile App Download ad, the counting period is fixed as 30days after clicked.
・For the measurement of the phone call conversion, you must setting the "conversion tracking tag" and "on-click event tag" on your site.<br>The installation method of "on-click event tag", please check Sponsored Search help pages.<br>
https://help.marketing.yahoo.co.jp/en/?p=363<br>

Please also refer Sponsored Search help pages for Conversion Analytics:<br>
https://help.marketing.yahoo.co.jp/en/?p=367
## get
Describes the operation which provide at ConversionTrackerService

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [ConversionTrackerSelector](../data/ConversionTrackerSelector.md) | Operation elements for ConversionTracker informations. | 
##### Request Sample
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
### Response
Response Fields for normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [ConversionTrackerPage](../data/ConversionTrackerPage.md) | Page of lists of the requested ConversionTracker informations. | 
##### Response Sample
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
            <conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>APP_ANDROID_FIRST_OPEN_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>APP_ANDROID_DOWNLOAD_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>WEB_CONVERSION_TRACKER</conversionTrackerName>
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

## mutate (ADD)
Add ConversionTracker informations.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | Operation elements for ConversionTracker informations. | 

##### Request Sample
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

### Response
Response Fields for normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | Container for ConversionTracker information including operation results. | 

##### Response Sample
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
            <conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>APP_ANDROID_FIRST_OPEN_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>APP_ANDROID_DOWNLOAD_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>WEB_CONVERSION_TRACKER</conversionTrackerName>
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

## mutate (SET)
Update ConversionTracker informations.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [ConversionTrackerOperation](../data/ConversionTrackerOperation.md) | Operation elements for ConversionTracker informations. | 

##### Request Sample
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
### Response
Response Fields for normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [ConversionTrackerReturnValue](../data/ConversionTrackerReturnValue.md) | Container for ConversionTracker information including operation results. |

##### Response Sample
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
            <conversionTrackerName>APP_ANDROID_IN_APP_PURCHASE_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>APP_ANDROID_FIRST_OPEN_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>APP_ANDROID_DOWNLOAD_CONVERSION_TRACKER</conversionTrackerName>
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
            <conversionTrackerName>WEB_CONVERSION_TRACKER</conversionTrackerName>
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
