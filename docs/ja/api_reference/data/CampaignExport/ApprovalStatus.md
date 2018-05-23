# ApprovalStatus (enum)
ApprovalStatusは、審査状況を表します。

### Service
+ [CampaignExportService](../../services/CampaignExportService.md)

### Namespace
[CampaignExportService#Namespace](../../services/CampaignExportService.md#namespace)

| Enumeration | Type | Description |
|---|---|---|
| APPROVED| string| 承認済です。 |
| APPROVED_WITH_REVIEW| string| 承認済です。<br>すでに掲載中のキーワード・広告を再編集し、審査中となり、編集前の広告が掲載されています。 |
| REVIEW| string| 審査中です。<br>新しく追加したキーワード・広告が審査中となり、広告は未掲載です。 |
| PRE_DISAPPROVED| string| 掲載不可です。<br>新しく追加したキーワード・広告が審査で承認されず非掲載です。 |
| POST_DISAPPROVED| string| 掲載停止です。<br>すでに掲載中のキーワード・広告について審査が行われた結果、承認されず非掲載です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
