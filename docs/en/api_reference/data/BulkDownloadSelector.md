# BulkDownloadSelector
Definition for target of bulk downloading.
### Service
+ [BulkService](../services/BulkService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| This field shows Account ID. |
| campaignIds[]| xsd:long| This field shows Campaign ID. |
| campaignCriterionIds[]| xsd:long| This field shows Campaign Criterion ID. |
| adGroupIds[]| xsd:long| This field shows Ad Group ID. |
| adIds[]| xsd:long| This field shows Ad ID. |
| adGroupCriterionIds[]| xsd:long| This field shows Ad Group Criterion ID. |
| campaignUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| This field specifies campaign status. |
| adGroupUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| This field specifies Ad Group status. |
| adGroupAdUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| This field specifies Ad status. |
| adGroupCriterionUserStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| This field specifies Ad Group Criterion status. |
| adGroupAdApprovalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| This field specifies Ad Group Approval status. |
| adGroupCriterionApprovalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| This field specifies Ad Group Criterion Approval Status. |
| entityTypes| enum <a href="../data/BulkEntityType.md">BulkEntityType</a>| This field specifies Entity. |
| downloadBulkJob| <a href="../data/DownloadBulkJob.md">DownloadBulkJob</a>| This field specifies download bulk job. |
| lang| enum <a href="../data/BulkLang.md">BulkLang</a>| This field indicates language. |
| output| enum <a href="../data/BulkOutput.md">BulkOutput</a>| This field specifies output format. |
| encoding| enum <a href="../data/BulkEncoding.md">BulkEncoding</a>| This field specifies character code for bulk sheet. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
