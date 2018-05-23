# ReportService
ReportService is to get, add, or delete  information of reports.<br>
And it provides the operation to download URL of the reports.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/ReportService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/ReportService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V201805/Report

#### Service Overview
The following operations are provided:
- Get reports
- Add reports
- Delete reports

[Maximum number of report download job]
- Up to 50 report download job that is saved as one-time report (Add Template: NO) can be added for regular and proxy authentications combined.<br>
- There is no upper limits to the number of report download jobs that is saved as scheduled report (Add Template: YES).
Example：<br>
If you have already saved 40 report download jobs for regular authentication, you can add a maximum of 10 jobs for proxy authentication.<br>
*If you wish to add more jobs though the upper saving limit is reached, delete some of the download jobs you already saved.<br>

[Notes]<br>
- Reports can be downloaded from the URL created with 'get' method.<br>
 The URL is valid in the first 5 minutes after the status becomes COMPLETED.
- Report download jobs will be automatically deleted after a week (7 days) from requested.<br>
#### Operation
Explains the operation which will be provided at ReportService.

#### Operation
Describes the operation which provides at ReportService.
+ [get](#get)
+ [mutate(ADD)](#mutate-add)
+ [mutate(REMOVE)](#mutate-remove)

#### Object
[Report](../data/Report)

## get
Gets the list of report that meets the selector criteria.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| selector | Req | [ReportSelector](../data/Report/ReportSelector.md) | Determines which report to return. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>100000001</accountId>
        <reportIds>1111</reportIds>
        <reportIds>1112</reportIds>
        <reportTypes>ACCOUNT</reportTypes>
        <reportTypes>CAMPAIGN</reportTypes>
        <reportTypes>ADGROUP</reportTypes>
        <reportTypes>AD</reportTypes>
        <reportTypes>KEYWORDS</reportTypes>
        <reportTypes>SEARCH_QUERY</reportTypes>
        <reportTypes>GEO</reportTypes>
        <reportTypes>FEED_ITEM</reportTypes>
        <reportTypes>GEO_TARGET</reportTypes>
        <reportTypes>SCHEDULE_TARGET</reportTypes>
        <reportTypes>BID_STRATEGY</reportTypes>
        <reportTypes>AD_CUSTOMIZERS</reportTypes>
        <reportTypes>TARGET_LIST</reportTypes>
        <reportTypes>LANDING_PAGE_URL</reportTypes>
        <reportJobStatuses>WAIT</reportJobStatuses>
        <reportJobStatuses>COMPLETED</reportJobStatuses>
        <reportJobStatuses>IN_PROGRESS</reportJobStatuses>
        <reportJobStatuses>FAILED</reportJobStatuses>
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
Response Fields in normal cases.

| Field | Data Type | Description |
|---|---|---|
| rval | [ReportPage](../data/Report/ReportPage.md) | Entries of the reports to be got.|

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1523506336544</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Report">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <Page.Type>ReportPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1111</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
            <ns2:completeTime>2017/11/27 14:33:20</ns2:completeTime>
            <ns2:reportDownloadURL>https://ss.yahooapis.jp/report/V201805/download/3CRAGObSahcIylBoDZS5ftx7qS4VM5jSHqs77QZqmpBFnJFP2jvKe3Dy72UEX3InsUoShWXa3YcX3AmbtqxGco6B</ns2:reportDownloadURL>
          </ns2:reportRecord>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1112</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report2</ns2:reportName>
            <ns2:reportJobStatus>FAILED</ns2:reportJobStatus>
            <ns2:reportJobErrorDetail>INTERNAL_ERROR</ns2:reportJobErrorDetail>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1113</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report3</ns2:reportName>
            <ns2:reportJobStatus>IN_PROGRESS</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1114</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report3</ns2:reportName>
            <ns2:reportJobStatus>WAIT</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Adds report.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [ReportOperation](../data/Report/ReportOperation.md) | List of reports to be operated including operation details. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/Report">
      <operations>
        <operator>ADD</operator>
        <accountId>11111</accountId>
        <operand>
          <reportId>2222</reportId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields in normal cases.

| Field | Data Type | Description |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | Container of reports including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1523506336555</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Report">
      <ns2:rval>
        <ListReturnValue.Type>ReportReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1113</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report3</ns2:reportName>
            <ns2:reportJobStatus>IN_PROGRESS</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
Deletes reports.

### Request
| Parameter | Restrictions | Data Type | Description |
|---|---|---|---|
| operations | Req | [ReportOperation](../data/Report/ReportOperation.md) | List of reports to be operated and operation details. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/Report">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <reportId>2222</reportId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields in normal cases.

| Field | Data Type | Description |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | Container of reports including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1523506336569</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Report">
      <ns2:rval>
        <ListReturnValue.Type>ReportReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>2222</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
            <ns2:completeTime>2017/11/27 14:33:20</ns2:completeTime>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
