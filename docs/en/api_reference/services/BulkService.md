# BulkService
BulkService is for bulk downloading/uploading by using bulk sheet.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/BulkService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/BulkService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Bulk downloading/uploading by using bulk sheet.

【Download process】<br>
1. Request data for bulk downloading by using getBulkDownload. <br>
2. Acquire downloadBulkJobId (bulk ID) included in the response.<br>
3. Check the status with getBulkDownloadStatus by using the bulk ID you acquire.<br>
4. Download URL comes back in the response if the status is “COMPLETED”.<br>
5. Check the status for a certain period if the status is “IN_PROGRESS”. <br>
6. Download URL does not come back if the status is “SYSTEM_ERROR” then another request for bulk download is needed.<br>
7. Request for bulk downloading again if the status is “TIMEOUT”. If there is still a problem on the request, please contact with API support staff at Yahoo Japan Corporation.<br>
<br>
【Caution】<br>
・Download URL is valid only for 15 minutes for security reason. <br>
　If 15 minutes passes after the URL is acquired, please request to get a new download URL again by using getBulkDownload. <br>
・The deleted account and campaign information are not included in the download file.<br>
・Please make sure using the same IP address that create the URL with getBulkDownload for the downloading.<br>
<br>
<br>
【Upload process】<br>
1. Request URL for bulk uploading by using getUploadUrl.<br>
2. The URL for uploading is responded.<br>
3. Process bulk uploading to upload URL.<br>
4. Acquire uploadBulkJobId(bulk ID) in the HTTP response when the upload process is completed.<br>
5. Acquire upload status by using getBulkUploadStatus based on uploadBulkJobId.<br>
6. The upload process is successfully completed if the status is “COMPLETED”.<br>
7. Check the status for a certain period if the status is “IN_PROGRESS”.<br>
<br>
【Caution】<br>
・Upload URL is valid only for 15 minutes for security reason. If 15 minutes passes after the URL is acquired, please request to get a new upload URL again by using getUploadUrl. <br>
・Please make sure using the same IP address that create the URL with getUploadUrl for the uploading.<br>
・The next file cannot be uploaded until the permission process for the previous upload is completed.<br>
・Multiple bulk sheets cannot be uploaded at the same time, including management console. <br>
　The maximum file size per uploading is 20MB, and the number of maximum line per day is 150,000 lines.<br>

#### Operation
Describes operations provided by BulkService.
## getBulkDownload
### Request
Defines a bulk download target.

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [BulkDownloadSelector](../data/BulkDownloadSelector.md) | Defines a bulk acquisition target. | 
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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
      <ns1:getBulkDownload>
      <ns1:selector>
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
        <ns1:downloadBulkJob>
          <ns1:downloadBulkJobName>ダウンロードジョブ</ns1:downloadBulkJobName>
        </ns1:downloadBulkJob>
        <ns1:lang>JA</ns1:lang>
        <ns1:output>CSV</ns1:output>
        <ns1:encoding>SJIS</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
      <ns1:getBulkDownload>
      <ns1:selector>
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
        <ns1:downloadBulkJob>
          <ns1:downloadBulkJobName>ダウンロードジョブ</ns1:downloadBulkJobName>
        </ns1:downloadBulkJob>
        <ns1:lang>JA</ns1:lang>
        <ns1:output>CSV</ns1:output>
        <ns1:encoding>SJIS</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/BulkDownloadReturnValue.md) | A container that stores results of download. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>BulkService</ns1:service>
      <ns1:remainingQuota>129984</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>1.1229</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownloadResponse>
      <ns1:rval>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:downloadBulkJob>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:downloadBulkJobId>42</ns1:downloadBulkJobId>
            <ns1:downloadBulkUserName>8983-5689-9971-5970</ns1:downloadBulkUserName>
            <ns1:downloadBulkStartDate>2011-09-07T22:55:37+09:00</ns1:downloadBulkStartDate>
            <ns1:downloadJobStatus>IN_PROGRESS</ns1:downloadJobStatus>
            <ns1:progress>0</ns1:progress>
          </ns1:downloadBulkJob>
        </ns1:values>
      </ns1:rval>
    </ns1:getBulkDownloadResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getBulkDownloadStatus
### Request
Checks the bulk download process status and acquires download source URL.

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [BulkDownloadStatusSelector](../data/BulkDownloadStatusSelector.md) | Defines a target for acquisition. |

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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkDownloadStatus>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobStatuses>COMPLETED</ns1:downloadBulkJobStatuses>
                <ns1:downloadBulkJobStatuses>IN_PROGRESS</ns1:downloadBulkJobStatuses>
            </ns1:selector>
        </ns1:getBulkDownloadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
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
        <ns1:getBulkDownloadStatus>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobStatuses>COMPLETED</ns1:downloadBulkJobStatuses>
                <ns1:downloadBulkJobStatuses>IN_PROGRESS</ns1:downloadBulkJobStatuses>
            </ns1:selector>
        </ns1:getBulkDownloadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadStatusPage](../data/BulkDownloadStatusPage.md) | The container including process status of target. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>BulkService</ns1:service>
      <ns1:remainingQuota>129997</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>3.995</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownloadStatusResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>BulkDownloadStatusPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:downloadBulkJob>
            <ns1:accountId>1000000380</ns1:accountId>
            <ns1:downloadBulkJobId>1</ns1:downloadBulkJobId>
            <ns1:downloadBulkUserName>8983-5689-9971-5970</ns1:downloadBulkUserName>
            <ns1:downloadBulkStartDate>2011-09-06T23:53:08+09:00</ns1:downloadBulkStartDate>
            <ns1:downloadBulkEndDate>2011-09-06T23:53:30+09:00</ns1:downloadBulkEndDate>
            <ns1:progress>100</ns1:progress>
            <ns1:downloadJobStatus>COMPLETED</ns1:downloadJobStatus>
            <ns1:downloadBulkDownloadUrl>https ://colo05.ss.yahooapis.jp/bulkDownload/V5.0/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadBulkDownloadUrl>
          </ns1:downloadBulkJob>
        </ns1:values>
      </ns1:rval>
    </ns1:getBulkDownloadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## getBulkUploadUrl
### Request
Indicate the URL for bulk uploading.

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| accountId | Req | xsd:long | Account ID. | 

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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getUploadUrl>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:getUploadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
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
        <ns1:getUploadUrl>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:getUploadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [UploadUrlValue](../data/UploadUrlValue.md) | The container including upload URL. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>BulkService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getUploadUrlResponse>
            <ns1:rval>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:acceptableUploadStatus>true</ns1:acceptableUploadStatus>
                <ns1:uploadUrl>https://sample.api.yahooapis.jp/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:uploadUrl>
            </ns1:rval>
        </ns1:getUploadUrlResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getBulkUploadStatus
### Request
Display the process status of bulk uploading.

| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [BulkUploadStatusSelector](../data/BulkUploadStatusSelector.md) | Specify the condition to acquire process status. | 

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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkUploadStatus>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:uploadBulkJobIds>12323230</ns1:uploadBulkJobIds>
                <ns1:uploadBulkJobStatuses>COMPLETED</ns1:uploadBulkJobStatuses> 
                <ns1:uploadBulkJobStatuses>IN_PROGRESS</ns1:uploadBulkJobStatuses> 
                <ns1:lang>EN</ns1:lang>
                <ns1:output>XML</ns1:output>
                <ns1:encoding>UTF-8</ns1:encoding>
            </ns1:selector>
        </ns1:getBulkUploadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account)
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
        <ns1:getBulkUploadStatus>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:uploadBulkJobIds>12323230</ns1:uploadBulkJobIds>
                <ns1:uploadBulkJobStatuses>COMPLETED</ns1:uploadBulkJobStatuses> 
                <ns1:uploadBulkJobStatuses>IN_PROGRESS</ns1:uploadBulkJobStatuses> 
                <ns1:lang>EN</ns1:lang>
                <ns1:output>XML</ns1:output>
                <ns1:encoding>UTF-8</ns1:encoding>
            </ns1:selector>
        </ns1:getBulkUploadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [BulkUploadStatusPage](../data/BulkUploadStatusPage.md) | Container for the job result of bulk uploading. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>BulkService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkUploadStatusResponse>
            <ns1:rval>
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>BulkUploadStatusPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:uploadBulkJob>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:uploadBulkJobId>xxxxxxxxxx</ns1:uploadBulkJobId>
                        <ns1:uploadBulkUserName>xxxxxxxxxx</ns1:uploadBulkUserName>
                        <ns1:uploadBulkStartDate>2011-10-18T15:29:11+09:00</ns1:uploadBulkStartDate>
                        <ns1:uploadBulkEndDate>2011-10-18T15:29:20+09:00</ns1:uploadBulkEndDate>
                        <ns1:uploadBulkJobStatus>COMPLETED</ns1:uploadBulkJobStatus>
                        <ns1:processingItemsCount>
                        <ns1:campaignCount>0</ns1:campaignCount>
                        <ns1:negativeCampaignCriterionCount>0</ns1:negativeCampaignCriterionCount>
                        <ns1:adGroupCount>0</ns1:adGroupCount>
                        <ns1:negativeAdGroupCriterionCount>0</ns1:negativeAdGroupCriterionCount>
                        <ns1:biddableAdGroupCriterionCount>0</ns1:biddableAdGroupCriterionCount>
                        <ns1:adGroupAdCount>0</ns1:adGroupAdCount>
                        <ns1:campaignErrorCount>18</ns1:campaignErrorCount>
                        <ns1:negativeCampaignCriterionErrorCount>0</ns1:negativeCampaignCriterionErrorCount>
                        <ns1:adGroupErrorCount>0</ns1:adGroupErrorCount>
                        <ns1:negativeAdGroupCriterionErrorCount>0</ns1:negativeAdGroupCriterionErrorCount>
                        <ns1:biddableAdGroupCriterionErrorCount>0</ns1:biddableAdGroupCriterionErrorCount>
                        <ns1:adGroupAdErrorCount>0</ns1:adGroupAdErrorCount>
                        </ns1:processingItemsCount>
                        <ns1:progress>100</ns1:progress>
                        <ns1:bulkDownloadUrl></ns1:bulkDownloadUrl>
                    </ns1:uploadBulkJob>
                </ns1:values>
            </ns1:rval>
        </ns1:getBulkUploadStatusResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
