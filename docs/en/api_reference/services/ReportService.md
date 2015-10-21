# ReportService
Use this service to get, add, or delete  reports.
And it provides the operation to download URL of the reports.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/ReportService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/ReportService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Use this service to get, add, or delete reports.
#### Operation
Explains the operation which will be provided at ReportService.
## get
### Request
Gets the list of report that meets the selector criteria.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [ReportSelector](../data/ReportSelector.md) | Determines which report to return. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:reportIds>100000003</ns1:reportIds>
                <ns1:reportIds>100000007</ns1:reportIds>
                <ns1:reportIds>100000005</ns1:reportIds>
                <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
                <ns1:reportJobStatuses>INPROGRESS</ns1:reportJobStatuses>
                <ns1:paging>
                    <ns1:startIndex>0</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### Response
Response Fields

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [reportPage](../data/reportPage.md) | A list of report where each entry in the list is the result of applying the operation in the input list with the same index. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
            <ns1:rval>
                <ns1:Page.Type>ReportPage</ns1:Page.Type>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>INPROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>INPROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate (ADD)
### Request
Adds report.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [ReportOperation](../data/ReportOperation.md) | A list of unique operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignIds/>
                    <ns1:adGroupIds/>
                    <ns1:kwIds/>
                    <ns1:adIds/>
                    <ns1:reportName>REPORT</ns1:reportName>
                    <ns1:reportType>ACCOUNT</ns1:reportType>
                    <ns1:dateRangeType>TODAY</ns1:dateRangeType>
                    <ns1:sort>+AVERAGECPC</ns1:sort>
                    <ns1:format>XML</ns1:format>
                    <ns1:encode>UTF-8</ns1:encode>
                    <ns1:zip>ON</ns1:zip>
                    <ns1:lang>EN</ns1:lang>
                    <ns1:addTemplate>YES</ns1:addTemplate>
                    <ns1:frequency>ONETIME</ns1:frequency>
                    <ns1:fields>DESCRIPTION</ns1:fields>
                    <ns1:fields>DESCRIPTION2</ns1:fields>
                    <ns1:fields>CLICKS</ns1:fields>
                    <ns1:fields>TOTALREVENUE</ns1:fields>
                    <ns1:fields>COST</ns1:fields>
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
| rval | [ReportReturnValue](../data/ReportReturnValue.md) | The list of added reports. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>INPROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>INPROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
### Request
Deletes reports.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [ReportOperation](../data/ReportOperation.md) | A list of unique operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportJobId>10000000001</ns1:reportJobId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:reportJobId>10000000002</ns1:reportJobId>
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
| rval | [ReportReturnValue](../data/ReportReturnValue.md) | The list of removed reports. |

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                    </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:reportJobId>200000002</ns1:reportJobId>
                    </ns1:reportRecord>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getDownloadUrl
### Request
Get download URL to import reports.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [ReportDownloadUrlSelector](../data/ReportDownloadUrlSelector.md) | The selector specifying the query. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        <ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getDownloadUrl>
            <ns1:selector>
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:reportJobIds>100000003</ns1:reportJobIds>
                <ns1:reportJobIds>100000007</ns1:reportJobIds>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:getDownloadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDownloadUrlPage](../data/ReportDownloadUrlPage.md) | List of report download URL. |

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getDownloadUrlResponse>
            <ns1:rval>
                <ns1:Page.Type>ReportDownloadUrlPage</ns1:Page.Type>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDownloadUrl>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>COMPLETED</ns1:status>
                        <ns1:downloadUrl>https://col06.ss.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl>
                    </ns1:reportDownloadUrl>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDownloadUrl>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>COMPLETED</ns1:status>
                        <ns1:downloadUrl>https://col06.ss.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl>
                    </ns1:reportDownloadUrl>
                </ns1:values>
            </ns1:rval>
        </ns1:getDownloadUrlResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
