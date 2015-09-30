# BulkDownloadStatusSelector
BulkDownloadStatusSelector object describes job status of bulk downloading.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID |
| downloadBulkJobIds[]| xsd:long| The bulk ID for downloads retrieved with getBulkDownload. |
| downloadBulkJobStatuses[]| enum <a href="./DownloadBulkJobStatus.md">DownloadBulkJobStatus</a>| Job status of bulk downloading |
| page| <a href="./Paging.md">Paging</a>| Page to be returned as the Response |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
