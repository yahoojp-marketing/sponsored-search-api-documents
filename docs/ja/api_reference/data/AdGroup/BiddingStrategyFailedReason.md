# BiddingStrategyFailedReason (enum)
BiddingStrategyFailedReasonは、自動入札設定の結果（失敗原因）です。

### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Enumeration | Type | Description |
|---|---|---|
| FAILURE| string| 原因不明です。 |
| CONVERSION_TRACKING_NOT_ENABLED| string| コンバージョン測定タグが発行されていません。 |
| NOT_ENOUGH_CONVERSIONS| string| コンバージョンの情報が十分でありません。 |
| CANNOT_CREATE_CAMPAIGN_WITH_CONVERSION_OPTIMIZER| string| コンバージョンオプティマイザーの情報は作成不可です。 |
| BIDDING_STRATEGY_CANNOT_BE_OVERRIDDEN| string| 自動入札設定の上書きができません。 |
| NOT_CPC_CAMPAIGN| string| 手動入札ではありません。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
