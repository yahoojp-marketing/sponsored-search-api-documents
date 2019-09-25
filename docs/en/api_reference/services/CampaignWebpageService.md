# CampaignWebpageService
CampaignWebpageService provides excluded settings of PageFeedItem for campaign.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/CampaignWebpageService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/CampaignWebpageService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201909/CampaignWebpage

#### Overview
Use this service to set excluded settings of PageFeedItem for campaign. <br>
- Set excluded settings of PageFeedItem for campaign.
- Remove PageFeedItem associated with campaign.
- Get PageFeedItem setting in campaign.

#### Operation
Describes the operation which provides by CampaignWebpageService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[CampaignWebpage](../data/CampaignWebpage)

## get
Get PageFeedItem setting in campaign.

#### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [CampaignWebpageSelector](../data/CampaignWebpage/CampaignWebpageSelector.md) | Condition to be acquired by get  operation. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>100000001</accountId>
        <campaignIds>1111</campaignIds>
        <campaignIds>2222</campaignIds>
        <campaignIds>3333</campaignIds>
        <targetIds>4444</targetIds>
        <targetIds>5555</targetIds>
        <targetIds>6666</targetIds>
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
| Filed | Data Type | Description |
|---|---|---|
| rval | [CampaignWebpagePage](../data/CampaignWebpage/CampaignWebpagePage.md) | Entries corresponding to conditions. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignWebpage</ns2:service>
      <ns2:requestTime>1547793769698</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignWebpage">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>CampaignWebpagePage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:webpage>
              <ns2:targetId>4444</ns2:targetId>
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
          </ns2:campaignWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Set excluded settings of PageFeedItem for campaign.

#### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignWebpageOperation](../data/CampaignWebpage/CampaignWebpageOperation.md) | Campaign to be set and PageFeedItem. | |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage">
      <operations>
        <operator>ADD</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
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
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Filed | Data Type | Description |
|---|---|---|
| rval | [CampaignWebpageReturnValue](../data/CampaignWebpage/CampaignWebpageReturnValue.md) | Result of setting. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignWebpage</ns2:service>
      <ns2:requestTime>1547793769717</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignWebpage">
      <ns2:rval>
        <ListReturnValue.Type>CampaignWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:webpage>
              <ns2:targetId>4444</ns2:targetId>
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
          </ns2:campaignWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove PageFeedItem associated with campaign.

#### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignWebpageOperation](../data/CampaignWebpage/CampaignWebpageOperation.md) | Campaign to remove and PageFeedItem. | |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage">
      <operations>
        <operator>REMOVE</operator>
        <accountId>100000001</accountId>
        <operand>
          <campaignId>1111</campaignId>
          <webpage>
            <targetId>4444</targetId>
          </webpage>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Response
| Filed | Data Type | Description |
|---|---|---|
| rval | [CampaignWebpageReturnValue](../data/CampaignWebpage/CampaignWebpageReturnValue.md) | Result of removing. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/CampaignWebpage" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>CampaignWebpage</ns2:service>
      <ns2:requestTime>1547793769737</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/CampaignWebpage">
      <ns2:rval>
        <ListReturnValue.Type>CampaignWebpageReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignWebpage>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:campaignId>1111</ns2:campaignId>
            <ns2:webpage>
              <ns2:targetId>4444</ns2:targetId>
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
          </ns2:campaignWebpage>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
