# PropPlatformTarget
PropPlatformTarget object is a container of device type and bid adjustments for traffic estimation.
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| Field | Data Type | Description | 
|---|---|---|
| platformName| <a href="../data/PlatformType.md">PlatformType</a>| Device type name. |
| bidMultiplier| xsd:double| Can adjust bid. Value: 0 or 0.10 ~ 4.00.<br>- 0: -100%(No ad delivery on smartphone)<br> - 0.10 ~ 4.00: -90% ~ +300% (Adjustment on smartphone)<br>*Enter up to two decimal places (e.g. 2.57)<br>*Error will return if the value is off range, or value is entered more than two decimal |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
