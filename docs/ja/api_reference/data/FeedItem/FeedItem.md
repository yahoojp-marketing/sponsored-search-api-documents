

# FeedItem

FeedItemオブジェクトは、フィードアイテム情報を格納します。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | - | Ignore | Ignore | Ignore | |
| feedFolderId | xsd:long | フィードフォルダIDです。 | yes | - | Ignore<br/>※アドカスタマイザーの場合、Requirement | Ignore | Ignore | |
| feedItemId | xsd:long | フィードアイテムIDです。 | yes | - | Ignore | Requirement | Requirement | |
| feedItemTrackId | xsd:long | トラッキング用フィードアイテムIDです。<br/>※Sandbox環境では常に0が返ります。 | yes | - | Ignore | Ignore | Ignore | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | 審査ステータスです。 | yes | - | Ignore | Ignore | Ignore | |
| disapprovalReasonCodes[0...n] | xsd:string | 審査否認理由です。 | yes | - | Ignore | Ignore | Ignore | |
| trademarkStatus | enum [TrademarkStatus](./TrademarkStatus.md) | 商標保護ステータス | yes | - | Ignore | Ignore | Ignore | |
| invalidedTrademarks[0...n] | xsd:string | 制限された商標 | yes | - | Ignore | Ignore | Ignore | |
| feedItemAttribute[0...20] | [FeedItemAttribute](./FeedItemAttribute.md)<br>inherited [SimpleFeedItemAttribute](./SimpleFeedItemAttribute.md)<br>inherited [MultipleFeedItemAttribute](./MultipleFeedItemAttribute.md) | フィードアイテムの属性情報です。 | yes | - | Requirement | Optional | Ignore | |
| placeholderType | enum [FeedItemPlaceholderType](./FeedItemPlaceholderType.md) | フィードアイテムの種類です。 | yes | - | Ignore | Ignore | Ignore | |
| devicePreference | enum [DevicePreference](./DevicePreference.md) | 優先デバイス設定です。<br/>※空で設定すると、既存の優先 デバイス設定は削除されます（電話番号以外のみ）。 | yes | - | Optional<br/>※電話番号オプションの場合、Optional<br/>※Default: SMART_PHONE | Optional<br/>※電話番号オプションの場合、Ignore | Ignore | |
| startDate | xsd:string | 配信開始日です。<br/>※空で設定すると、既存の配信開始日は削除されます。 | yes | - | Optional | Optional | Ignore | |
| endDate | xsd:string | 配信終了日です。<br/>※空で設定すると、既存の配信終了日は削除されます。 | yes | - | Optional | Optional | Ignore | |
| scheduling | [FeedItemScheduling](./FeedItemScheduling.md) | 配信スケジュールです。<br/>※空で設定すると、既存の配信スケジュールは削除されます。 | yes | - | Optional | Optional | Ignore | |
| targetingCampaign | [TargetingCampaign](./TargetingCampaign.md) | アドカスタマイザーで使用するキャンペーンです。 | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | |
| targetingAdGroup | [TargetingAdGroup](./TargetingAdGroup.md) | アドカスタマイザーで使用する広告グループです。 | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | |
| targetingKeyword | [TargetingKeyword](./TargetingKeyword.md) | アドカスタマイザーで使用するキーワードです。 | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | |
| customParameters | [CustomParameters](./CustomParameters.md) | カスタムパラメータです。 | yes | - | Ignore<br/>※クイックリンクオプションの場合、Optional | Ignore<br/>※クイックリンクオプションの場合、Optional | Ignore | |
| reviewCustomParameters | [CustomParameters](./CustomParameters.md) | 配信審査中のカスタムパラメータです。 | yes | - | Ignore | Ignore | Ignore | |
| geoTargeting | [Location](./Location.md) | 地域設定情報です。 | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
