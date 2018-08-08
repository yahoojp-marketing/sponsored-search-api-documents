# CampaignSharedSetService
CampaignSharedSetService setup Negative keyword list to campaign.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201808/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201808/AdGroupAdService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201808/AdGroupAd

#### Overview
Use this service to setup Negative keyword list to campaign.

#### Operation
Describe the operation which provides at CampaignSharedSetService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[CampaignSharedSet](../data/CampaignSharedSet)

## get
Returns the setup information between campaign and negative keyword list.

### Request
| Parameter | Restrictions| Data Type | Description |
|---|---|---|---|
| selector | Req | [CampaignSharedSetSelector](../data/AdGroupAd/CampaignSharedSetSelector.md) | This is object which holds the search criteria (exec parameters) on get method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>111111</accountId>
        <campaignIds>44</campaignIds>
        <sharedListIds>22</sharedListIds>
        <sharedListIds>33</sharedListIds>
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

| Field | Data Type | Description |
|---|---|---|
| rval | [CampaignSharedSetPage](../data/AdGroupAd/CampaignSharedSetPage.md) | This is object which holds the exec result (List of all entities) of get method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>CampaignSharedSet</ns2:service>
      <ns2:requestTime>1523506332508</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/CampaignSharedSet">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignSharedSet>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>11</ns2:sharedListId>
            <ns2:campaignId>44</ns2:campaignId>
            <ns2:sharedListName>sample</ns2:sharedListName>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
          </ns2:campaignSharedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Setup negative keyword list for campaign.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignSharedSetOperation](../data/AdGroupAd/CampaignSharedSetOperation.md) | The object which holds setup information of campaign and negative keyword list for the operation by mutate method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet">
      <operations>
        <operator>ADD</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>11</sharedListId>
          <campaignId>44</campaignId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [CampaignSharedSetReturnValue](../data/AdGroupAd/CampaignSharedSetReturnValue.md) | This is object which holds the exec result (List of all entities) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>CampaignSharedSet</ns2:service>
      <ns2:requestTime>1523506332525</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/CampaignSharedSet">
      <ns2:rval>
        <ListReturnValue.Type>CampaignSharedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignSharedSet>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:campaignId>44</ns2:campaignId>
            <ns2:sharedListName>sample</ns2:sharedListName>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
          </ns2:campaignSharedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove the setup settings between campaign and negative keyword list.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [CampaignSharedSetOperation](../data/AdGroupAd/CampaignSharedSetOperation.md) |The object which holds setup information of campaign and negative keyword list for the operation by mutate method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1111</accountId>
        <operand>
          <sharedListId>2222</sharedListId>
          <campaignId>3333</campaignId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response field

| Field | Data Type | Description |
|---|---|---|
| rval | [CampaignSharedSetReturnValue](../data/AdGroupAd/CampaignSharedSetReturnValue.md) |This is object which holds the exec result (List of all entities) of mutate method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/CampaignSharedSet" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>CampaignSharedSet</ns2:service>
      <ns2:requestTime>1523506332539</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/CampaignSharedSet">
      <ns2:rval>
        <ListReturnValue.Type>CampaignSharedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:campaignSharedSet>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:sharedListId>22</ns2:sharedListId>
            <ns2:campaignId>44</ns2:campaignId>
            <ns2:sharedListName>sample</ns2:sharedListName>
            <ns2:campaignName>sample campaign.</ns2:campaignName>
          </ns2:campaignSharedSet>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
