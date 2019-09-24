# LabelService
Use this service to get, add, update or remove information of label.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201909/LabelService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201909/LabelService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V201909/Label

#### Overview
Use this service to get, add, update or remove information of label.

#### Operation
Describe the operation which provides at LabelService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[Label](../data/Label)

## get
Gets information related to labels.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [LabelSelector](../data/Label/LabelSelector.md) | The label selector for operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <selector>
        <accountId>1234567890</accountId>
        <labelIds>10001</labelIds>
        <labelIds>10002</labelIds>
        <labelIds>10003</labelIds>
        <labelIds>10004</labelIds>
        <labelIds>10005</labelIds>
        <countLabeledEntity>TRUE</countLabeledEntity>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>1000</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description |
|---|---|---|
| rval | [LabelPage](../data/Label/LabelPage.md) | Entry of acquired label. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>Label</ns2:service>
      <ns2:requestTime>1547793090271</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/Label">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>LabelPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:label>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:labelId>10001</ns2:labelId>
            <ns2:labelName>sample label.</ns2:labelName>
            <ns2:description>sample description.</ns2:description>
            <ns2:color>#FF0000</ns2:color>
            <ns2:labeledCampaign>0</ns2:labeledCampaign>
            <ns2:labeledAdGroup>0</ns2:labeledAdGroup>
            <ns2:labeledAdGroupAd>0</ns2:labeledAdGroupAd>
            <ns2:labeledAdGroupCriterion>0</ns2:labeledAdGroupCriterion>
          </ns2:label>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Add label information.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [LabelOperation](../data/Label/LabelOperation.md) | The label selector for operations and list of operations.  |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/Label">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <labelName>sample_20190918153130262</labelName>
          <description>add sample</description>
          <color>#000000</color>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields.

| Field | Data Type | Description |
|---|---|---|
| rval | [LabelReturnValue](../data/Label/LabelReturnValue.md) | This object is a container for label which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>Label</ns2:service>
      <ns2:requestTime>1547793090286</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/Label">
      <ns2:rval>
        <ListReturnValue.Type>LabelReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:label>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:labelId>10001</ns2:labelId>
            <ns2:labelName>sample_20190918153130262</ns2:labelName>
            <ns2:description>add sample</ns2:description>
            <ns2:color>#000000</ns2:color>
          </ns2:label>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Updates the information related to labels.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [LabelOperation](../data/Label/LabelOperation.md) | The label selector for operations and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/Label">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <labelId>10001</labelId>
          <labelName>set sample_20190918153130262</labelName>
          <description>set sample</description>
          <color>#ffffff</color>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields.

| Field | Data Type | Description |
|---|---|---|
| rval | [LabelReturnValue](../data/Label/LabelReturnValue.md) | This object is a container for label which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>Label</ns2:service>
      <ns2:requestTime>1547793090301</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/Label">
      <ns2:rval>
        <ListReturnValue.Type>LabelReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:label>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:labelId>10001</ns2:labelId>
            <ns2:labelName>set sample_20190918153130262</ns2:labelName>
            <ns2:description>set sample</ns2:description>
            <ns2:color>#ffffff</ns2:color>
            <ns2:labeledCampaign>0</ns2:labeledCampaign>
            <ns2:labeledAdGroup>0</ns2:labeledAdGroup>
            <ns2:labeledAdGroupAd>0</ns2:labeledAdGroupAd>
            <ns2:labeledAdGroupCriterion>0</ns2:labeledAdGroupCriterion>
          </ns2:label>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Removes the inforamtion related to labels.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [LabelOperation](../data/Label/LabelOperation.md) | The label selector for operations and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201909/Label">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <labelId>10001</labelId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields.

| Field | Data Type | Description |
|---|---|---|
| rval | [LabelReturnValue](../data/Label/LabelReturnValue.md) | This object is a container for label which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201909/Label" xmlns:ns2="http://ss.yahooapis.jp/V201909">
      <ns2:service>Label</ns2:service>
      <ns2:requestTime>1547793090318</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201909" xmlns:ns2="http://ss.yahooapis.jp/V201909/Label">
      <ns2:rval>
        <ListReturnValue.Type>LabelReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:label>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:labelId>10001</ns2:labelId>
            <ns2:labelName>set sample_20190918153130262</ns2:labelName>
            <ns2:description>set sample</ns2:description>
            <ns2:color>#ffffff</ns2:color>
            <ns2:labeledCampaign>0</ns2:labeledCampaign>
            <ns2:labeledAdGroup>0</ns2:labeledAdGroup>
            <ns2:labeledAdGroupAd>0</ns2:labeledAdGroupAd>
            <ns2:labeledAdGroupCriterion>0</ns2:labeledAdGroupCriterion>
          </ns2:label>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
