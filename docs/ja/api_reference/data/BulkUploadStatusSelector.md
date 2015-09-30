# BulkUploadStatusSelector
BulkUploadStatusSelectorオブジェクトは、一括アップロードの処理状況を指定します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| uploadBulkJobIds[]| xsd:long| アップロードのバルクジョブIDです。 |
| uploadBulkJobStatuses[]| enum <a href="../data/UploadBulkJobStatus.md">UploadBulkJobStatus</a>| アップロードの処理状況を指定します。 |
| lang| enum <a href="../data/BulkLang.md">BulkLang</a>| レスポンスに含まれる、エラー出力用バルクシートの言語を指定します。 |
| output| enum <a href="../data/BulkOutput.md">BulkOutput</a>| レスポンスに含まれる、エラー出力用バルクシートの出力フォーマットを指定します。 |
| encoding| enum <a href="../data/BulkEncoding.md">BulkEncoding</a>| レスポンスに含まれる、エラー出力用バルクシートの文字コードを指定します。 |
| page| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
