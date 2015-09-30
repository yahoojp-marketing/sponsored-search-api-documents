# UploadBulkJob
UploadBulkJobオブジェクトは、アップロードジョブの内容を表します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| uploadBulkJobId| xsd:long| アップロードのバルクジョブIDです。 |
| uploadBulkJobName| xsd:string| アップロードのバルクジョブ名です。 |
| uploadBulkJobStatus| enum <a href="../data/UploadBulkJobStatus.md">UploadBulkJobStatus</a>| アップロードのバルク処理の状況です。 |
| processingItemsCount| <a href="../data/ProcessingItemsCount.md">ProcessingItemsCount</a>| 処理を行った数を格納するコンテナです。 |
| downloadBulkUploadFileUrl| xsd:string| アップロードした処理結果ファイルをダウンロードするURLです。 |
| downloadBulkUploadErrorFileUrl| xsd:string| アップロードに失敗した結果ファイルをダウンロードするURLです。 |
| progress| xsd:int| 進捗率です。<br>1-100の整数です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
