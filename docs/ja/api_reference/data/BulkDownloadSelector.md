# BulkDownloadSelector
BulkDownloadSelectorオブジェクトは、一括ダウンロードする対象を定義します。
### Service
+ [BulkService](../services/BulkService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignIds[]| xsd:long| キャンペーンIDです。 |
| campaignCriterionIds[]| xsd:long| キャンペーンクライテリアIDです。 |
| adGroupIds[]| xsd:long| 広告グループIDです。 |
| adIds[]| xsd:long| 広告IDです。 |
| adGroupCriterionIds[]| xsd:long| 広告グループクライテリアIDです。 |
| campaignUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| キャンペーンの状態の指定です。 |
| adGroupUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| 広告グループの状態の指定です。 |
| adGroupAdUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| 広告の状態の指定です。 |
| adGroupCriterionUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| 広告グループクライテリアの状態の指定です。 |
| adGroupAdApprovalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| 広告グループの審査状況の指定です。 |
| adGroupCriterionApprovalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| 広告グループクライテリアの審査状況の指定です。 |
| entityTypes| enum <a href="../data/BulkEntityType.md">BulkEntityType</a>| エンティティの指定です。 |
| downloadBulkJob| <a href="../data/DownloadBulkJob.md">DownloadBulkJob</a>| ダウンロードのバルクジョブの指定です。 |
| lang| enum <a href="../data/BulkLang.md">BulkLang</a>| ダウンロードするバルクシート言語を指定します。 |
| output| enum <a href="../data/BulkOutput.md">BulkOutput</a>| ダウンロードするバルクシートの出力フォーマットの指定を指定します。 |
| encoding| enum <a href="../data/BulkEncoding.md">BulkEncoding</a>| バルクシートの文字コードを指定します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
