# FeedFolderService
FeedFolderService is to get, add, update, or remove the FeedFolder (Data auto insertion) information.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/FeedFolderService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/FeedFolderService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Overview
Use this service to get, add, upgrade, or remove the FeedFolder (Data auto insertion) information.
#### Operation
Describes the operation which provides by FeedFolderService.
## get
Returns Feed Folder information.
### Request

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | Req | [FeedFolderSelector](../data/FeedFolderSelector.md) | The list information of FeedFolder (Data auto insertion) information. | 

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:feedFolderIds>12</ns1:feedFolderIds>
                <ns1:feedFolderIds>13</ns1:feedFolderIds>
                <ns1:feedFolderIds>14</ns1:feedFolderIds>
                <ns1:feedFolderName>FeedFolderName</ns1:feedFolderName>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:feedFolderIds>12</ns1:feedFolderIds>
                <ns1:feedFolderIds>13</ns1:feedFolderIds>
                <ns1:feedFolderIds>14</ns1:feedFolderIds>
                <ns1:feedFolderName>FeedFolderName</ns1:feedFolderName>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields
| Field | Data Type | Description | 
|---|---|---|
| rval | [FeedFolderPage](../data/FeedFolderPage.md) | Entry of acquired list information related to FeedFolder (Data auto insertion) information. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
               <ns1:totalNumEntries>3</ns1:totalNumEntries>
                <ns1:Page.Type>FeedFolderPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
Add the information related to Feed Folder.
### Request

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | Req | [FeedFolderOperation](../data/FeedFolderOperation.md) | The list information of FeedFolder (Data auto insertion) information for operations and list of operations. | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                    </ns1:feedAttribute>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                    </ns1:feedAttribute>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample (On-Behalf-Of Account)
```xml	
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                    </ns1:feedAttribute>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                    </ns1:feedAttribute>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields
| Field | Data Type | Description | 
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolderReturnValue.md) | This object is a container for FeedFolder (Data auto insertion) information which includes operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedFolderReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Updates Feed Folder information.
### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [FeedFolderOperation](../data/FeedFolderOperation.md) | The list information of FeedFolder (Data auto insertion) information for operations and and list of operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                    </ns1:feedAttribute>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                    </ns1:feedAttribute>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                    </ns1:feedAttribute>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                    </ns1:feedAttribute>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields
| Field | Data type | Description | 
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolderReturnValue.md) | This object is a container for FeedFolder (Data auto insertion) information which includes operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedFolderReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
Removes Feed Folder information.
### Request

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [FeedFolderOperation](../data/FeedFolderOperation.md) | FeedFolder (Data auto insertion) information for operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderId>100000001</ns1:feedFolderId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderId>100000001</ns1:feedFolderId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields
| Field | Data type | Description | 
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolderReturnValue.md) | This object is a container for list information of FeedFolder (Data auto insertion) information which includes operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedFolderReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholderType>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER</ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feedAttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE</ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
