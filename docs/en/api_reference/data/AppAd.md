# AppAd
Apps ad excluding for smartphone.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | Description | add | set| remove|
|---|---|---|---|---|---|
| Ad(inherited)||||||
| type| enum <a href="./AdType.md">AdType</a>| This field indicates the subtype of Ad of this instance.| Ignore| Ignore| Ignore |
| url| xsd:string| Destination URL.| Req| Req<br>Updatable| Ignore |
| displayUrl| xsd:string| Display URL| Req| Req<br>Updatable| Ignore |
| headline| xsd:string| The Title of the ad.| Req| Req<br>Updatable| Ignore |
| description| xsd:string| The description of the ad.| Req| Ignore| Ignore |
| AppAd||||||
| description2| xsd:string| The description2 of the ad.| Req| Ignore| Ignore |
| appStore| enum <a href="./AppStore_AdGroupAd.md">AppStore</a>| The list of Apps ad.<br>* Automatically the Mobile app download ID will set for Mobile app download| Ignore*| Ignore| Ignore |
| appId| xsd:string| Apps ID or Package name.<br>* Automatically the Mobile app download ID will set for Mobile app download| Ignore*| Ignore| Ignore |
| devicePreference| enum <a href="./DevicePreference.md">DevicePreference</a>| Device preference<br>* Only for Smartphone| Opt| Ignore| Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
