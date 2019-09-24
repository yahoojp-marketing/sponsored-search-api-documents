

# AdGroupAd

AdGroupAd object describes information for operations on ads.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | - | Ignore | Ignore | Ignore | |
| campaignId | xsd:long | Campaign ID. | yes | - | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | |
| campaignTrackId | xsd:long | Campaign ID for tracking.<br/>* &#34;0&#34; will return in Sandbox. | yes | - | Ignore | Ignore | Ignore | |
| campaignName | xsd:string | Campaign name. | yes | - | Ignore | Ignore | Ignore | |
| adGroupId | xsd:long | Ad group ID. | yes | - | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | |
| adGroupTrackId | xsd:long | Ad group ID for tracking.<br/>* &#34;0&#34; will return in Sandbox. | yes | - | Ignore | Ignore | Ignore | |
| adGroupName | xsd:string | Ad group name. | yes | - | Ignore | Ignore | Ignore | |
| adId | xsd:long | Ad ID. | yes | - | Ignore | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | |
| adTrackId | xsd:long | Ad ID for tracking.<br/>* &#34;0&#34; will return in Sandbox. | yes | - | Ignore | Ignore | Ignore | |
| adName | xsd:string | Ad name. | yes | - | Requirement | Optional<br/><i>Updatable</i> | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | Status of ad that been set.<br/>* If there is no designation, all ads in all condition will return. | yes | - | Requirement | Optional<br/><i>Updatable</i> | Ignore | |
| trademarkStatus | enum [TrademarkStatus](./TrademarkStatus.md) | Trademark status. | yes | - | Ignore | Ignore | Ignore | |
| invalidedTrademarks[0...n] | xsd:string | Invalided trademarks. | yes | - | Ignore | Ignore | Ignore | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | Editorial review status. | yes | - | Ignore | Ignore | Ignore | |
| disapprovalReasonCodes | xsd:string | Code of Disapproval reason. | yes | - | Ignore | Ignore | Ignore | |
| ad | [Ad](./Ad.md)<br>inherited [TextAd2](./TextAd2.md)<br>inherited [AppAd](./AppAd.md)<br>inherited [ExtendedTextAd](./ExtendedTextAd.md)<br>inherited [DynamicSearchLinkedAd](./DynamicSearchLinkedAd.md) | Details of creative ad. | yes | - | Requirement | Ignore | Ignore | |
| feedFolderId | xsd:long | Feed folder ID. | yes | - | Ignore | Ignore | Ignore | |
| labels[0..50] | [Label](./Label.md) | Label | yes | Ignore | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
