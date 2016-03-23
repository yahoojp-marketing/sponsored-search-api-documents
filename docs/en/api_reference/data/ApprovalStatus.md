# ApprovalStatus (enum)
ApprovalStatus displays Editorial Status.

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignExportService](../services/CampaignExportService.md)
+ [FeedItemService](../services/FeedItemService.md)

| Value | Data Type | Description | 
|---|---|---|
| APPROVED| string| The item is approved |
| APPROVED_WITH_REVIEW| string| The item is approved<br>Updated items are under review |
| REVIEW| string| Under editorial review<br>Newly added keywords/ads are under review, and not displayed yet |
| PRE_DISAPPROVED| string| The item was rejected<br>Newly added keywords/ads have been rejected, so it cannot be displayed |
| POST_DISAPPROVED| string| The item was rejected<br>Ads already displayed have been taken offline due to a result from post review |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
