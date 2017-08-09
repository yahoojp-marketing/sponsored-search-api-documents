# AuditLogService
AuditLogService provides the feature to download operation history data.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AuditLogService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AuditLogService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Use this service to download operation history data.

#### Operation
Describes the operation which is provided by AuditLogService.

## get
Get the download URL for operation history data.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [AuditLogSelector](../data/AuditLogSelector.md) | This object retains search criterias to inquire an added job. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
           <ns1:accountId>12345</ns1:accountId>
           <ns1:jobIds>1000</ns1:jobIds>
           <ns1:jobIds>1001</ns1:jobIds>
           <ns1:jobStatuses>IN_PROGRESS</ns1:jobStatuses>
           <ns1:jobStatuses>COMPLETED</ns1:jobStatuses>
         <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>100</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [AuditLogPage](../data/AuditLogPage.md) | This object retains the operation result of get method. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>AuditLogService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.001</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>AuditLogPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:job>
                  <ns1:accountId>12345</ns1:accountId>
                  <ns1:jobId>1000</ns1:jobId>
                  <ns1:jobName>Sample AuditLog Job 1</ns1:jobName>
                  <ns1:jobStatus>COMPLETED</ns1:jobStatus>
                  <ns1:downloadUrl>https://colo01.ss.yahooapis.jp/audit/V6.3/download/xxxxxxxxxxxxxxxxxxxxxxxxxxxx</ns1:downloadUrl>
                  <ns1:dateRange>
                     <ns1:startDate>20170701120000</ns1:startDate>
                     <ns1:endDate>20170701235959</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:sourceType>API</ns1:sourceType>
                  <ns1:output>TSV</ns1:output>
                  <ns1:encoding>UTF_8</ns1:encoding>
                  <ns1:lang>JA</ns1:lang>
               </ns1:job>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:job>
                  <ns1:accountId>12345</ns1:accountId>
                  <ns1:jobId>1001</ns1:jobId>
                  <ns1:jobName>Sample AuditLog Job 2</ns1:jobName>
                  <ns1:jobStatus>IN_PROGRESS</ns1:jobStatus>
                  <ns1:dateRange>
                     <ns1:startDate>20170701120000</ns1:startDate>
                     <ns1:endDate>20170701235959</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:sourceType>YAHOO_JAPAN</ns1:sourceType>
                  <ns1:output>CSV</ns1:output>
                  <ns1:encoding>UTF_8</ns1:encoding>
                  <ns1:lang>EN</ns1:lang>
               </ns1:job>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## addJob
Add a job to download operation history data file.<br>

### Request
| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [AuditLogJobOperation](../data/AuditLogJobOperation.md) | This object retains the job to be added. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:addJob>
         <ns1:operations>
            <ns1:accountId>12345</ns1:accountId>
           <ns1:operand>
               <ns1:jobName>Sample AuditLog Job 1</ns1:jobName>
              <ns1:eventSelector>
                  <ns1:entityType>AD</ns1:entityType>
                  <ns1:eventTypes>ADD</ns1:eventTypes>
                  <ns1:eventTypes>REMOVE</ns1:eventTypes>
               </ns1:eventSelector>
              <ns1:eventSelector>
                  <ns1:entityType>BIDDABLE_AD_GROUP_CRITERION</ns1:entityType>
                  <ns1:eventTypes>ALL</ns1:eventTypes>
               </ns1:eventSelector>
              <ns1:eventSelector>
                  <ns1:entityType>NEGATVIE_AD_GROUP_CRITERION</ns1:entityType>
                  <ns1:eventTypes>ALL</ns1:eventTypes>
               </ns1:eventSelector>              
               <ns1:dateRange>
                  <ns1:startDate>20170701120000</ns1:startDate>
                  <ns1:endDate>20170701235959</ns1:endDate>
               </ns1:dateRange>
               <ns1:sourceType>API</ns1:sourceType>
               <ns1:output>TSV</ns1:output>
               <ns1:encoding>UTF_8</ns1:encoding>
               <ns1:lang>JA</ns1:lang>
            </ns1:operand>
          <ns1:operand>
               <ns1:jobName>Sample AuditLog Job 1</ns1:jobName>
              <ns1:eventSelector>
                  <ns1:entityType>ALL</ns1:entityType>
                  <ns1:eventTypes>ALL</ns1:eventTypes>
               </ns1:eventSelector>
               <ns1:dateRange>
                  <ns1:startDate>20170701120000</ns1:startDate>
                  <ns1:endDate>20170701235959</ns1:endDate>
               </ns1:dateRange>
               <ns1:sourceType>YAHOO_JAPAN</ns1:sourceType>
               <ns1:output>CSV</ns1:output>
               <ns1:encoding>UTF_8</ns1:encoding>
               <ns1:lang>EN</ns1:lang>
            </ns1:operand>          
         </ns1:operations>
      </ns1:addJob>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [AuditLogReturnValue](../data/AuditLogReturnValue.md) | This object retains the operation result of addJob method. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>AuditLogService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.001</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:addJobResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>AuditLogReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>AddJob</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:job>
                  <ns1:accountId>12345</ns1:accountId>
                  <ns1:jobId>1000</ns1:jobId>
                  <ns1:jobName>Sample AuditLog Job 1</ns1:jobName>
                  <ns1:jobStatus>IN_PROGRESS</ns1:jobStatus>
                  <ns1:dateRange>
                     <ns1:startDate>20170701120000</ns1:startDate>
                     <ns1:endDate>20170701235959</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:sourceType>USER</ns1:sourceType>
                  <ns1:output>TSV</ns1:output>
                  <ns1:encoding>UTF_8</ns1:encoding>
                  <ns1:lang>JA</ns1:lang>
               </ns1:job>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:job>
                  <ns1:accountId>12345</ns1:accountId>
                  <ns1:jobId>1001</ns1:jobId>
                  <ns1:jobName>Sample AuditLog Job 2</ns1:jobName>
                  <ns1:jobStatus>IN_PROGRESS</ns1:jobStatus>
                  <ns1:dateRange>
                     <ns1:startDate>20170701120000</ns1:startDate>
                     <ns1:endDate>20170701235959</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:sourceType>YAHOO_JAPAN</ns1:sourceType>
                  <ns1:output>CSV</ns1:output>
                  <ns1:encoding>UTF_8</ns1:encoding>
                  <ns1:lang>EN</ns1:lang>
               </ns1:job>
            </ns1:values>
         </ns1:rval>
      </ns1:addJobResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## download
Download operation history data file from the URL which acruiqred by 'get'.<br>

### Request

##### Request Sample
```xml
https://colo[01-12].ss.yahooapis.jp/audit/V6.3/download/xxxxxxxxxxxxxxxxxxxxxxxxxxxx
```


<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
