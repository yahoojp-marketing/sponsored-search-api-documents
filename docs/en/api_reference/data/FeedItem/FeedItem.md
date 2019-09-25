

# FeedItem

FeedItem object contains the information of Feed Item.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID | yes | - | Ignore | Ignore | Ignore | |
| feedFolderId | xsd:long | Feed Folder ID | yes | - | Ignore<br/>※アドカスタマイザーの場合、Requirement | Ignore | Ignore | |
| feedItemId | xsd:long | Feed Item ID | yes | - | Ignore | Requirement | Requirement | |
| feedItemTrackId | xsd:long | Feed Item ID for tracking<br/>∗In Sandbox,&#34;0&#34; will return. | yes | - | Ignore | Ignore | Ignore | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | Review status | yes | - | Ignore | Ignore | Ignore | |
| disapprovalReasonCodes[0...n] | xsd:string | Reject reason on editorial review | yes | - | Ignore | Ignore | Ignore | |
| trademarkStatus | enum [TrademarkStatus](./TrademarkStatus.md) | Trademark status. | yes | - | Ignore | Ignore | Ignore | |
| invalidedTrademarks[0...n] | xsd:string | Invalided trademarks. | yes | - | Ignore | Ignore | Ignore | |
| feedItemAttribute[0...20] | [FeedItemAttribute](./FeedItemAttribute.md)<br>inherited [SimpleFeedItemAttribute](./SimpleFeedItemAttribute.md)<br>inherited [MultipleFeedItemAttribute](./MultipleFeedItemAttribute.md) | Attribute of Feed Item | yes | - | Requirement | Optional | Ignore | |
| placeholderType | enum [FeedItemPlaceholderType](./FeedItemPlaceholderType.md) | Type of Feed Item | yes | - | Ignore | Ignore | Ignore | |
| devicePreference | enum [DevicePreference](./DevicePreference.md) | The settings of Focus Device<br/>∗On setting blank, existing focus device setting will be deleted (excluding Call Extension). | yes | - | Optional<br/>※電話番号オプションの場合、Optional<br/>※Default: SMART_PHONE | Optional<br/>※電話番号オプションの場合、Ignore | Ignore | |
| startDate | xsd:string | Start date of ad display<br/>∗On setting blank, existing start date of ad display will be deleted | yes | - | Optional | Optional | Ignore | |
| endDate | xsd:string | End date of ad display<br/>∗On setting blank, existing end date of ad display will be deleted | yes | - | Optional | Optional | Ignore | |
| scheduling | [FeedItemScheduling](./FeedItemScheduling.md) | Ad display schedule<br/>∗On setting blank, existing ad display schedule will be deleted | yes | - | Optional | Optional | Ignore | |
| targetingCampaign | [TargetingCampaign](./TargetingCampaign.md) | Campaign used for Ad Customizer | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | |
| targetingAdGroup | [TargetingAdGroup](./TargetingAdGroup.md) | Ad Group used for Ad Customizer | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | |
| targetingKeyword | [TargetingKeyword](./TargetingKeyword.md) | Keyword used for Ad Customizer | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | |
| customParameters | [CustomParameters](./CustomParameters.md) | Custom parameters | yes | - | Ignore<br/>※クイックリンクオプションの場合、Optional | Ignore<br/>※クイックリンクオプションの場合、Optional | Ignore | |
| reviewCustomParameters | [CustomParameters](./CustomParameters.md) | Custom parameters in review | yes | - | Ignore | Ignore | Ignore | |
| geoTargeting | [Location](./Location.md) | Geographic Location | yes | - | Ignore<br/>※アドカスタマイザーの場合、Optional | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
