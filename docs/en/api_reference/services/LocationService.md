# LocationService
Use this service to retrieve the URL prefix for the colocation your account is assigned to.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/LocationService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/LocationService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/Location
#### Overview
LocationService provides an operation that returns the URL prefix for the colocation your account is assigned to. <br>
Before using, please make sure to understand how to send the request to LocationService.
#### Operation
By using main URL send the request via LocationService.
Main URL is shown at WSDL of LocationService.

+ [get](#get)

#### Object
[LocationService](../data/Location)

## get
### LocationService
Send the request by using local URL. <br>
To create local URL, get the prefix part of collocation URL for the account by using the Location Service. <br>
Then, create URL by combing URL Prefix part and current version and specified service name.<br>
In addition, there is no specific rule on the effective period of the location information, so we recommend that you create the colocation when it is expired, and not to create it everytime you operate.

### Request
| Field | Restrictions | Data Type | Description |
|---|---|---|---|
| accountId | Req | xsd:long | Account ID. |
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V201805/Location">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Location" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/Location">
      <accountId>1234567890</accountId>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [LocationReturnValue](../data/Location/LocationReturnValue.md) | A page (subset) view of the location selected. |
##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Location" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Location</ns2:service>
      <ns2:requestTime>1522056589052</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Location">
      <ns2:rval>
        <operationSucceeded>true</operationSucceeded>
        <ns2:value>https://ss.yahooapis.jp/xxx</ns2:value>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
