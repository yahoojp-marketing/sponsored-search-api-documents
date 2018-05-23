# FeedFolderService
FeedFolderService is to get, add, update, or remove the FeedFolder (Data auto insertion) information.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/FeedFolderService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/FeedFolderService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V201805/FeedFolder
#### Overview
Use this service to get, add, upgrade, or remove the FeedFolder (Data auto insertion) information.
#### Operation
Describes the operation which provides by FeedFolderService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(SET)](#mutateset)
+ [mutate(REMOVE)](#mutateremove)

#### Object
[FeedFolder](../data/FeedFolder)

## get
Returns Feed Folder information.

### Request

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | Req | [FeedFolderSelector](../data/FeedFolder/FeedFolderSelector.md) | The list information of FeedFolder (Data auto insertion) information. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>1234567890</accountId>
        <feedFolderIds>10001</feedFolderIds>
        <feedFolderIds>10002</feedFolderIds>
        <feedFolderIds>10003</feedFolderIds>
        <feedFolderIds>10004</feedFolderIds>
        <feedFolderIds>10005</feedFolderIds>
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
| rval | [FeedFolderPage](../data/FeedFolder/FeedFolderPage.md) | Entry of acquired list information related to FeedFolder (Data auto insertion) information. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1523506333557</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/FeedFolder">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>FeedFolderPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Add the information related to Feed Folder.

### Request

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedFolderOperation](../data/FeedFolder/FeedFolderOperation.md) | The list information of FeedFolder (Data auto insertion) information for operations and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/FeedFolder">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <feedFolderName>test feedFolder.</feedFolderName>
          <feedAttribute>
            <feedAttributeName>integerFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_INTEGER</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>priceFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_PRICE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>dateFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_DATE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>stringFeedAttribute</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_STRING</placeholderField>
          </feedAttribute>
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
| rval | [FeedFolderReturnValue](../data/FeedFolder/FeedFolderReturnValue.md) | This object is a container for FeedFolder (Data auto insertion) information which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1523506333569</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/FeedFolder">
      <ns2:rval>
        <ListReturnValue.Type>FeedFolderReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Updates Feed Folder information.

### Request

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedFolderOperation](../data/FeedFolder/FeedFolderOperation.md) | The list information of FeedFolder (Data auto insertion) information for operations and and list of operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/FeedFolder">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <feedFolderId>10001</feedFolderId>
          <feedAttribute>
            <feedAttributeName>integerFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_INTEGER</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>priceFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_PRICE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>dateFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_DATE</placeholderField>
          </feedAttribute>
          <feedAttribute>
            <feedAttributeName>stringFeedAttribute2</feedAttributeName>
            <placeholderField>AD_CUSTOMIZER_STRING</placeholderField>
          </feedAttribute>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields
| Field | Data type | Description |
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolder/FeedFolderReturnValue.md) | This object is a container for FeedFolder (Data auto insertion) information which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1523506333583</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/FeedFolder">
      <ns2:rval>
        <ListReturnValue.Type>FeedFolderReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>5</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>6</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>7</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>8</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Removes Feed Folder information.

### Request

| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [FeedFolderOperation](../data/FeedFolder/FeedFolderOperation.md) | FeedFolder (Data auto insertion) information for operations. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/FeedFolder">
      <operations>
        <operator>REMOVE</operator>
        <accountId>1234567890</accountId>
        <operand>
          <accountId>0</accountId>
          <feedFolderId>10001</feedFolderId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields
| Field | Data type | Description |
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolder/FeedFolderReturnValue.md) | This object is a container for list information of FeedFolder (Data auto insertion) information which includes operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/FeedFolder" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>FeedFolder</ns2:service>
      <ns2:requestTime>1523506333595</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/FeedFolder">
      <ns2:rval>
        <ListReturnValue.Type>FeedFolderReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFolder>
            <ns2:accountId>1234567890</ns2:accountId>
            <ns2:feedFolderId>10001</ns2:feedFolderId>
            <ns2:feedFolderName>test feedFolder.</ns2:feedFolderName>
            <ns2:placeholderType>AD_CUSTOMIZER</ns2:placeholderType>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>1</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>2</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>3</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>4</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>5</ns2:feedAttributeId>
              <ns2:feedAttributeName>integerFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_INTEGER</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>6</ns2:feedAttributeId>
              <ns2:feedAttributeName>priceFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_PRICE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>7</ns2:feedAttributeId>
              <ns2:feedAttributeName>dateFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_DATE</ns2:placeholderField>
            </ns2:feedAttribute>
            <ns2:feedAttribute>
              <ns2:feedAttributeId>8</ns2:feedAttributeId>
              <ns2:feedAttributeName>stringFeedAttribute2</ns2:feedAttributeName>
              <ns2:placeholderField>AD_CUSTOMIZER_STRING</ns2:placeholderField>
            </ns2:feedAttribute>
          </ns2:feedFolder>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
