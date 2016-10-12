# AdGroupBidMultiplier
AdGroupBidMultiplierオブジェクトは、入札価格調整率を表します。
### Service
+ [AdGroupBidMultiplierService](../services/AdGroupBidMultiplierService.md)

| Field | Type | Description | response | get | add | set | remove | 
|---|---|---|---|---|---|---|---|
| accountid| xsd:long| アカウントIDです。| ○ | - | - | Ignore | Ignore |
| campaignId| xsd:long| キャンペーンIDです。| ○ | - | - | Requirement | Requirement |
| adGroupId| xsd:long| 広告グループIDです。|  ○ | - | - | Requirement | Requirement |
| platformType| enum [PlatformType](../PlatformType.md)| 配信デバイスです。|  ○ | - | - | Requirement | Requirement |
| bidMultiplier| xsd:double| 入札調整率です。0～10.0まで指定できます。0を指定した場合、広告は配信されません。|  ○ | - | - | Requirement | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
