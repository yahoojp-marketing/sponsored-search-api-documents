# BulkUploadStatusSelector
BulkUploadStatusSelector object describes Job status of bulk uploading.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID |
| uploadBulkJobIds[]| xsd:long| Bulk Job ID for uploading. |
| uploadBulkJobStatuses[]| enum <a href="./UploadBulkJobStatus.md">UploadBulkJobStatus</a>| Specify job status for uploading. |
| lang| enum <a href="./BulkLang.md">BulkLang</a>| Indicate language for bulk error file |
| output| enum <a href="./BulkOutput.md">BulkOutput</a>| Indicate output format for bulk error file |
| encoding| enum <a href="./BulkEncoding.md">BulkEncoding</a>| Indicate character in bulk error file |
| page| <a href="./Paging.md">Paging</a>| Page to be returned as the Response |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
