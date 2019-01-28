# AdGroupCriterionLabelService
Use this service to add or remove related conditions (criteria) of ad group and label.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201901/AdGroupCriterionLabelService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201901/AdGroupCriterionLabelService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel

#### Overview
Use this service to add or remove related conditions (criteria) of ad group and label.

#### Operation
Describe the operation which provides at AdGroupCriterionLabelService.

+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[AdGroupCriterionLabel](../data/AdGroupCriterionLabel)

## mutate(ADD)
Add informations of related conditions (criteria) of ad group and label.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupCriterionLabelOperation](../data/AdGroupCriterionLabel/AdGroupCriterionLabelOperation.md) | Criteria of ad group and label for operation and process details. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <criterionId>30001</criterionId>
          <labelId>40001</labelId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupCriterionLabelReturnValue](../data/AdGroupCriterionLabel/AdGroupCriterionLabelReturnValue.md) | Container of ad group criteria and label information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupCriterionLabel</ns2:service>
      <ns2:requestTime>1547792997687</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupCriterionLabelReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterionLabel>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:criterionId>30001</ns2:criterionId>
            <ns2:labelId>40001</ns2:labelId>
          </ns2:adGroupCriterionLabel>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Remove informations of related conditions (criteria) of ad group and label.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [AdGroupCriterionLabelOperation](../data/AdGroupCriterionLabel/AdGroupCriterionLabelOperation.md) | Criteria of ad group and label for operation and process details. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <campaignId>10001</campaignId>
          <adGroupId>20001</adGroupId>
          <criterionId>30001</criterionId>
          <labelId>40001</labelId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description |
|---|---|---|
| rval | [AdGroupCriterionLabelReturnValue](../data/AdGroupCriterionLabel/AdGroupCriterionLabelReturnValue.md) | Container of ad group criteria and label information including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel" xmlns:ns2="http://ss.yahooapis.jp/V201901">
      <ns2:service>AdGroupCriterionLabel</ns2:service>
      <ns2:requestTime>1547792997777</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201901" xmlns:ns2="http://ss.yahooapis.jp/V201901/AdGroupCriterionLabel">
      <ns2:rval>
        <ListReturnValue.Type>AdGroupCriterionLabelReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:adGroupCriterionLabel>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:campaignId>10001</ns2:campaignId>
            <ns2:adGroupId>20001</ns2:adGroupId>
            <ns2:criterionId>30001</ns2:criterionId>
            <ns2:labelId>40001</ns2:labelId>
          </ns2:adGroupCriterionLabel>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
