# AdGroupWebpageService
AdGroupWebpageService provides allowed or excluded settings of PageFeedItem for ad group.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/AdGroupWebpageService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/AdGroupWebpageService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201808/AdGroupWebpage

#### Overview
Use this service to set allowed or excluded settings of PageFeedItem for ad group.
+ Set allowed or excluded settings of PageFeedItem for ad group.
+ Remove PageFeedItem associated with ad group.
+ Get PageFeedItem setting in ad group.

#### Operation
Describes the operation which provides by AdGroupWebpageService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[AdGroupWebpage](../data/AdGroupWebpage/AdGroupWebpage.md)

## get
Get allowed or excluded settings of PageFeedItem setting in ad group.

#### Request

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [AdGroupWebpageSelector](../data/AdGroupWebpage/AdGroupWebpageSelector.md) | Condition to be acquired by get operation. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>100000001</accountId>
        <campaignIds>1111</campaignIds>
        <campaignIds>2222</campaignIds>
        <campaignIds>3333</campaignIds>
        <adGroupIds>4444</adGroupIds>
        <adGroupIds>5555</adGroupIds>
        <adGroupIds>6666</adGroupIds>
        <targetIds>7777</targetIds>
        <targetIds>8888</targetIds>
        <targetIds>9999</targetIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>100</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data type | Description |
|---|---|---|
| rval | [AdGroupWebpagePage](../data/AdGroupWebpage/AdGroupWebpagePage.md) | Allowed or excluded settings of PageFeedItem corresponding to condition to be acquired by get operation. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1532512779934</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupWebpage">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AdGroupWebpagePage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Set allowed or excluded settings of PageFeedItem for ad group.<br>
&lowast; With one request, web page information can be set for ad group under different campaign.<br>
&lowast; Within one request, you can not set the same combination WebpageParameter to the same adGroupId.

#### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupWebpageOperation](../data/AdGroupWebpage/AdGroupWebpageOperation.md) | Allowed or excluded settings of ad group and PageFeedItem to be set. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
          <adGroupId>4444</adGroupId>
          <userStatus>ACTIVE</userStatus>
          <excludedType>INCLUDED</excludedType>
          <webpage>
            <parameter>
              <conditions>
                <type>URL</type>
                <argument>yahoo.co.jp</argument>
              </conditions>
              <conditions>
                <type>PAGE_TITLE</type>
                <argument>YahooJapan</argument>
              </conditions>
              <conditions>
                <type>CUSTOM_LABEL</type>
                <argument>sample</argument>
              </conditions>
            </parameter>
          </webpage>
          <bid>
            <maxCpc>100</maxCpc>
          </bid>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data type | Description |
|---|---|---|
| rval | [AdGroupWebpageReturnValue](../data/AdGroupWebpage/AdGroupWebpageReturnValue.md) | Allowed or excluded settings of PageFeedItem set to ad group including operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1532512780378</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupWebpage">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Set allowed or excluded settings of PageFeedItem for ad group.<br>
&lowast; With one request, web page information can be set for ad group under different campaign.<br>
&lowast; Within one request, you can not set the same combination WebpageParameter to the same adGroupId.

#### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupWebpageOperation](../data/AdGroupWebpage/AdGroupWebpageOperation.md) | Allowed or excluded setting of ad group and PageFeedItem to be set. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage">
      <operations>
        <operator>SET</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
          <adGroupId>4444</adGroupId>
          <userStatus>ACTIVE</userStatus>
          <excludedType>INCLUDED</excludedType>
          <webpage>
            <targetId>7777</targetId>
            <parameter>
              <conditions>
                <type>URL</type>
                <argument>yahoo.co.jp</argument>
              </conditions>
              <conditions>
                <type>PAGE_TITLE</type>
                <argument>YahooJapan</argument>
              </conditions>
              <conditions>
                <type>CUSTOM_LABEL</type>
                <argument>sample</argument>
              </conditions>
            </parameter>
          </webpage>
          <bid>
            <maxCpc>100</maxCpc>
          </bid>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data type | Description |
|---|---|---|
| rval | [AdGroupWebpageReturnValue](../data/AdGroupWebpage/AdGroupWebpageReturnValue.md) | Allowed or excluded settings of PageFeedItem set to ad group including operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1532512780457</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupWebpage">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove PageFeedItem associated with ad group.

#### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupWebpageOperation](../data/AdGroupWebpage/AdGroupWebpageOperation.md) | Allowed or excluded settings of ad group and PageFeedItem to be deleted. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
          <adGroupId>4444</adGroupId>
          <webpage>
            <targetId>7777</targetId>
          </webpage>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Field | Data type | Description |
|---|---|---|
| rval | [AdGroupWebpageReturnValue](../data/AdGroupWebpage/AdGroupWebpageReturnValue.md) | Allowed or excluded settings of PageFeedItem deleted from ad group including operation result. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/AdGroupWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>AdGroupWebpage</ns2:service>
      <ns2:requestTime>1532512780528</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/AdGroupWebpage">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:adGroupId>4444</ns2:adGroupId>
            <ns2:userStatus>ACTIVE</ns2:userStatus>
            <ns2:excludedType>INCLUDED</ns2:excludedType>
            <ns2:webpage>
              <ns2:targetId>7777</ns2:targetId>
              <ns2:parameter>
                <ns2:conditions>
                  <ns2:type>URL</ns2:type>
                  <ns2:argument>yahoo.co.jp</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>PAGE_TITLE</ns2:type>
                  <ns2:argument>YahooJapan</ns2:argument>
                </ns2:conditions>
                <ns2:conditions>
                  <ns2:type>CUSTOM_LABEL</ns2:type>
                  <ns2:argument>sample</ns2:argument>
                </ns2:conditions>
              </ns2:parameter>
            </ns2:webpage>
            <ns2:bid>
              <ns2:maxCpc>100</ns2:maxCpc>
            </ns2:bid>
          </ns2:adGroupWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
