# AdGroupBidMultiplier
Container for bid multiplier.
### Service
+ [AdGroupBidMultiplierService](../services/AdGroupBidMultiplierService.md)

| Field | Type | Description | response | get | add | set | remove | 
|---|---|---|---|---|---|---|---|
| accountid| xsd:long| Account ID.| ○ | - | - | Ignore | Ignore |
| campaignId| xsd:long| Campaign ID.| ○ | - | - | Requirement | Requirement |
| adGroupId| xsd:long| Ad group iD.|  ○ | - | - | Requirement | Requirement |
| platformType| enum [PlatformType](PlatformType.md)| Device type for ad delivery.|  ○ | - | - | Requirement | Requirement |
| bidMultiplier| xsd:double| Bid adjustment rate.<br>Can be specified between  0 to 10.0.<br>When specified '0', the ad will not be delievered.|  ○ | - | - | Requirement | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
