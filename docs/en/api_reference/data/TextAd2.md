# TextAd2
TextAd2 object is a text ad type for Sponsored Search on PC and smartphone.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data type | Description | 
|---|---|---|
| Ad(inherited)|||
| type| enum <a href="./AdType.md">AdType</a>| Ad type. （TEXT_AD2） |
| url| xsd:string| URL address. |
| displayUrl| xsd:string| Display URL. |
| headline| xsd:string| Title of the ad. |
| description| xsd:string| Description (line1) of the ad. |
| TextAd2|||
| description2| xsd:string| Description (line2) of the ad. |
| devicePreference| enum <a href="./DevicePreference.md">DevicePreference</a>| Appoint the high priority device in delivering ads. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
