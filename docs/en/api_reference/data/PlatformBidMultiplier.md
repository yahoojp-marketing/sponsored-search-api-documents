# PlatformBidMultiplier
Container for bid multiplier.
### Service
+ [AdGroupBidMultiplierService](../services/AdGroupBidMultiplierService.md)

| Field | Data Type | Description | SET | 
|---|---|---|---|
| type| enum <a href="./BidMultiplierType.md">BidMultiplierType</a>| Type for bid multiplier.| Req |
| platformName| enum <a href="./PlatformType.md">PlatformType</a>| Platform for bid multiplier.| Req |
| bidMultiplier| xsd:double| Can adjust bid. Value: 0 or 0.10 ~ 4.00.<br><br>- 0: -100%(No ad delivery on smartphone)<br><br>- 0.10 ~ 4.00: -90% ~ +300% (Adjustment on smartphone)<br><br>Enter up to two decimal places (e.g. 2.57)<br><br>Error will return if the value is off range, or value is entered more than two decimal| Optional<br><br>Updatable |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
