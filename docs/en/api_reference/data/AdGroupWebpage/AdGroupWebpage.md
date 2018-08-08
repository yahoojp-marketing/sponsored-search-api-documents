# AdGroupWebpage
AdGroupWebpage object contains information of allowed or excluded settings setup to adgroup.

### Service
+ [AdGroupWebpageService](../../services/AdGroupWebpageService.md)

### Namespace
[AdGroupWebpageService#Namespace](../../services/AdGroupWebpageService.md#namespace)

| Field | Type | Description | response | add | set | remove
|---|---|---|---|---|---|---|
| accountId | xsd:long | Account ID | yes | Ignore | Ignore | Ignore |
| campaignId | xsd:long | Campaign ID | yes | Req | Req | Req |
| campaignTrackId | xsd:long | Campaign Tracking ID	| yes | Ignore | Ignore | Ignore |
| adGroupId | xsd:long | Ad Group ID | yes | Req | Req | Req |
| adGroupTrackId | xsd:long | Ad Group Tracking ID | yes | Ignore | Ignore | Ignore |
| userStatus | enum [UserStatus](./UserStatus.md) | Display Status | yes | Optional | Optional<br>&lowast;ExcludedType can update only INCLUDED | Ignore |
| excludedType | enum [ExcludedType](./ExcludedType.md) | 'Allow' or 'Exclude' setting | yes | Optional<br>Default : INCLUDED | Ignore | Ignore |
| webpage | [Webpage](./Webpage.md) | Information of webpage | yes | Req | Req | Req |
| bid | [Bid](./Bid.md) | Bid | yes | Optional | Optional<br>&lowast;ExcludedType can update only INCLUDED | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
