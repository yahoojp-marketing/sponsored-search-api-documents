# CampaignExportService
CampaignExportService provides operations of collectively obtaining the campaign, ad group, keyword, and ad information.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V6.0/CampaignExportService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V6.0/CampaignExportService?wsdl|]

#### Namespace
http://ss.yahooapis.jp/V6

#### Overview
Collectively obtains the campaign, ad group, keyword, and ad information.

#### Operation
Describe the operation which provides at CampaignExportService.

## addJob
Creates job to register for export.

### Request

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [ExportSetting](../data/ExportSetting.md) | Details of conditions to export. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:addJob>
         <ns1:setting>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:campaignUserStatuses>ACTIVE</ns1:campaignUserStatuses>
            <ns1:adGroupUserStatuses>ACTIVE</ns1:adGroupUserStatuses>
            <ns1:adGroupAdUserStatuses>ACTIVE</ns1:adGroupAdUserStatuses>
            <ns1:adGroupCriterionUserStatuses>ACTIVE</ns1:adGroupCriterionUserStatuses>
            <ns1:adGroupAdApprovalStatuses>APPROVED</ns1:adGroupAdApprovalStatuses>
            <ns1:adGroupAdApprovalStatuses>APPROVED_WITH_REVIEW</ns1:adGroupAdApprovalStatuses>
            <ns1:adGroupAdApprovalStatuses>REVIEW</ns1:adGroupAdApprovalStatuses>
            <ns1:adGroupAdApprovalStatuses>PRE_DISAPPROVED</ns1:adGroupAdApprovalStatuses>
            <ns1:adGroupAdApprovalStatuses>POST_DISAPPROVED</ns1:adGroupAdApprovalStatuses>
            <ns1:adGroupCriterionApprovalStatuses>APPROVED</ns1:adGroupCriterionApprovalStatuses>
            <ns1:adGroupCriterionApprovalStatuses>APPROVED_WITH_REVIEW</ns1:adGroupCriterionApprovalStatuses>
            <ns1:adGroupCriterionApprovalStatuses>REVIEW</ns1:adGroupCriterionApprovalStatuses>
            <ns1:adGroupCriterionApprovalStatuses>PRE_DISAPPROVED</ns1:adGroupCriterionApprovalStatuses>
            <ns1:adGroupCriterionApprovalStatuses>POST_DISAPPROVED</ns1:adGroupCriterionApprovalStatuses>
            <ns1:entityTypes>ALL</ns1:entityTypes>
            <ns1:jobName>DownloadJob</ns1:jobName>
            <ns1:lang>JA</ns1:lang>
            <ns1:output>CSV</ns1:output>
            <ns1:encoding>SJIS</ns1:encoding>
            <ns1:advanced>FALSE</ns1:advanced>
         </ns1:setting>
      </ns1:addJob>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Field | Data Type | Description | 
|---|---|---|
| rval | [CampaignExportReturnValue](../data/CampaignExportReturnValue.md) | Container that includes operation result with export information. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>CampaignExportService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>1.1229</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:addJobResponse>
      <ns1:rval>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:job>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:jobId>42</ns1:jobId>
            <ns1:jobName>DownloadJob</ns1:jobName>
            <ns1:userName>8983-5689-9971-5970</ns1:userName>
            <ns1:startDate>2011-09-07T22:55:37+09:00</ns1:startDate>
            <ns1:status>IN_PROGRESS</ns1:status>
            <ns1:progress>0</ns1:progress>
          </ns1:job>
        </ns1:values>
      </ns1:rval>
    </ns1:addJobResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## get
Obtains the information of registered jobs.

### Request

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [JobSelector](../data/JobSelector.md) | Information of condition to search the registered export information. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:jobIds>xxxxxxxxxxxxxx</ns1:jobIds>
                <ns1:jobIds>xxxxxxxxxxxxxx</ns1:jobIds>
                <ns1:jobIds>xxxxxxxxxxxxxx</ns1:jobIds>
                <ns1:statuses>COMPLETED</ns1:statuses>
                <ns1:statuses>IN_PROGRESS</ns1:statuses>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Filed | Data Type | Description | 
|---|---|---|
| rval | [CampaignExportPage](../data/CampaignExportPage.md) | Details of obtainable registered export information. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>CampaignExportService</ns1:service>
      <ns1:remainingQuota>129997</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>3.995</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>CampaignExportPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:job>
            <ns1:accountId>1000000380</ns1:accountId>
            <ns1:jobId>1</ns1:jobId>
            <ns1:userName>8983-5689-9971-5970</ns1:userName>
            <ns1:startDate>2011-09-06T23:53:08+09:00</ns1:startDate>
            <ns1:endDate>2011-09-06T23:53:30+09:00</ns1:endDate>
            <ns1:progress>100</ns1:progress>
            <ns1:status>COMPLETED</ns1:status>
            <ns1:downloadUrl>https ://colo05.ss.yahooapis.jp/bulkDownload/V6/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl>
          </ns1:job>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
