# DownloadBulkJob
Definition of bulk job for downloading.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | DOWNLOAD | 
|---|---|---|---|
| accountId| xsd:long| Account ID.| Req |
| downloadBulkJobId| xsd:string| Bulk ID for download.| - |
| downloadBulkJobName| xsd:string| Bulk name for download.| Opt |
| downloadBulkUserName| xsd:string| User name for download.| - |
| downloadBulkStartDate| xsd:string| The start date of download.| - |
| downloadBulkEndDate| xsd:string| The end date of download.| - |
| downloadJobStatus| enum <a href="./DownloadBulkJobStatus.md">DownloadBulkJobStatus</a>| Download status.| - |
| progress| xsd:int| Progress status (1?100).| - |
| downloadBulkDownloadUrl| xsd:string| Download URL.| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
