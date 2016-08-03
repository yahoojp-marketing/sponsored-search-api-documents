# BidLandscapeService
BidLandscapeService estimates the change of an impression and a click when a bid price is changed.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/BidLandscapeService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/BidLandscapeService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Overview
Estimates the change of an impression and a click when a bid price is changed.
#### Operation
Explains the operations provided by BidLandscapeService.
## get
### Request
Estimate the change of an impression and a click when a bid price is changed.<br>
The maximum value of the selector criteria is 100.

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [BidLandscapeSelector](../data/BidLandscapeSelector.md) | This parameter designates an account, campaign, ad group and criteria subject to the operation. | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>aaaaaa</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>1000000380</ns1:accountId>
        <ns1:campaignId>1000000001</ns1:campaignId>
        <ns1:adGroupId>1000000001</ns1:adGroupId>
        <ns1:criterionIds>447</ns1:criterionIds>
        <ns1:criterionIds>448</ns1:criterionIds>
        <ns1:criterionIds>449</ns1:criterionIds>
        <ns1:criterionIds>450</ns1:criterionIds>
        <ns1:simType>ADGROUP</ns1:simType>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>aaaaaa</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
      <ns1:onBehalfOfAccountId>yyyyyyyyyyyyyy</ns1:onBehalfOfAccountId> 
      <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>1000000380</ns1:accountId>
        <ns1:campaignId>1000000001</ns1:campaignId>
        <ns1:adGroupId>1000000001</ns1:adGroupId>
        <ns1:criterionIds>447</ns1:criterionIds>
        <ns1:criterionIds>448</ns1:criterionIds>
        <ns1:criterionIds>449</ns1:criterionIds>
        <ns1:criterionIds>450</ns1:criterionIds>
        <ns1:simType>ADGROUP</ns1:simType>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [BidLandscapePage](../data/BidLandscapePage.md) | This parameter shows an entry for the acquired estimate. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>BidLandscapeService</ns1:service>
      <ns1:remainingQuota>99948</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>4</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>2.0236</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>BidLandscapePage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:data xsi:type="ns1:AdGroupBidLandscape">
            <ns1:campaignId>1000000001</ns1:campaignId>
            <ns1:adGroupId>1000000001</ns1:adGroupId>
            <ns1:landscapePoints>
              <ns1:bid>100</ns1:bid>
              <ns1:clicks>400</ns1:clicks>
              <ns1:cost>200</ns1:cost>
              <ns1:marginalCpc>300</ns1:marginalCpc>
              <ns1:impressions>500</ns1:impressions>
            </ns1:landscapePoints>
            <ns1:BidLandscape.Type>AdGroupBidLandscape</ns1:BidLandscape.Type>
            <ns1:type>DEFAULT</ns1:type>
            <ns1:landscapeCurrent>true</ns1:landscapeCurrent>
          </ns1:data>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
