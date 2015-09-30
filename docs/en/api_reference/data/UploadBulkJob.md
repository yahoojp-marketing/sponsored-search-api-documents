# UploadBulkJob
Details of upload.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd: long| Accoount ID. |
| uploadBulkJobId| xsd:long| Bulk job ID for uploading. |
| uploadBulkJobName| xsd:string| Buld job name for uploading. |
| uploadBulkJobStatus| enum <a href="../data/UploadBulkJobStatus.md">UploadBulkJobStatus</a>| Bulk job status for uploading. |
| processingItemsCount| <a href="../data/ProcessingItemsCount.md">ProcessingItemsCount</a>| The container for the number of  jobs. |
| downloadBulkUploadFileUrl| xsd:string| The URL to download the jobresult file for uploading. |
| downloadBulkUploadErrorFileUrl| xsd:string| The URL to download the failure report for uploading. |
| progress| xsd:int| Progress status (1-100) |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
