# AccountService
AccountService provides functions for creating and managing accounts.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AccountService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AccountService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Overview
AccountService provides operations for creating managing accounts.
#### Operation
Describe the operation which provides at Account Service.
## get
Returns an account. Enable to set the filter condition, such as the account Type.

### Request

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [AccountSelector](../data/AccountSelector.md) | Determines which accounts to retrive. If you omit account Ids field, return all of the accouns that you have access. (On-Behalf-of access is not support this function. You must specify account ID for On-Behalf-of access). | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        <ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountIds>100000001</ns1:accountIds>
                <ns1:accountTypes>PREPAY</ns1:accountTypes>
                <ns1:paging>
                    <ns1:startIndex>0</ns1:startIndex>
                    <ns1:numberResults>1</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        <ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountIds>100000001</ns1:accountIds>
                <ns1:accountTypes>PREPAY</ns1:accountTypes>
                <ns1:paging>
                    <ns1:startIndex>0</ns1:startIndex>
                    <ns1:numberResults>1</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Filed | Data Type | Description | 
|---|---|---|
| rval | [AccountPage](../data/AccountPage.md) | List of accounts identified by the selector. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
    xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AccountService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>AccountPage</ns1:Page.Type>
            <ns1:values>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:account>
                    <ns1:accountId>1000000000</ns1:accountId>
                    <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
                    <ns1:accountType>INVOICE</ns1:accountType>
                    <ns1:accountStatus>SERVING</ns1:accountStatus>
                    <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                    <ns1:budget>
                        <ns1:amount>1000000</ns1:amount>
                        <ns1:limitChargeType>SUM</ns1:limitChargeType>
                        <ns1:startDate>20091130</ns1:startDate>
                        <ns1:endDate>20100120</ns1:endDate>
                    </ns1:budget>
                </ns1:account>
            </ns1:values>
            <ns1:values>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:account>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
                    <ns1:accountType>INVOICE</ns1:accountType>
                    <ns1:accountStatus>SERVING</ns1:accountStatus>
                    <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                    <ns1:budget>
                        <ns1:amount>2000000</ns1:amount>
                        <ns1:limitChargeType>SUM</ns1:limitChargeType>
                        <ns1:startDate>20091031</ns1:startDate>
                        <ns1:endDate>20100320</ns1:endDate>
                    </ns1:budget>
                </ns1:account>
            </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
Updates the account.

### Request

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [AccountOperation](../data/AccountOperation.md) | The operations to apply. | 
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        <ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
                    <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        <ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
                    <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### Response

| Field | Data Type | Description | 
|---|---|---|
| rval | [AccountReturnValue](../data/AccountReturnValue.md) | The list of updated account. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
    xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
    xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>LocationService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AccountReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:account>
                        <ns1:accountId>1000000000</ns1:accountId>
                        <ns1:accountName>XXXXXXXXXXXXXX</ns1:accountName>
                        <ns1:accountType>INVOICE</ns1:accountType>
                        <ns1:accountStatus>SERVING</ns1:accountStatus>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:budget>
                            <ns1:amount>1000000</ns1:amount>
                            <ns1:limitChargeType>SUM</ns1:limitChargeType>
                            <ns1:startDate>20091130</ns1:startDate>
                            <ns1:endDate>20100120</ns1:endDate>
                        </ns1:budget>
                    </ns1:account>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
