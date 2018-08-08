# PageFeedItemApprovalStatus (enum)
PageFeedItemApprovalStatus displays Editorial Status.

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Enumeration | Type | Description |
|---|---|---|
| APPROVED | string | The item is approved |
| APPROVED_WITH_REVIEW | string | The item is approved<br>Updated items are under review |
| REVIEW | string | Under editorial review<br>Newly added keywords/ads are under review, and not displayed yet |
| PRE_DISAPPROVED| string| The item was rejected<br>Newly added keywords/ads have been rejected, so it cannot be displayed |
| POST_DISAPPROVED| string| The item was rejected<br>Ads already displayed have been taken offline due to a result from post review |


[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
