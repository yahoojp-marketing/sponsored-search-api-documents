# AppAd
Apps ad excluding for smartphone.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Ad(inherited)||||||
| type| enum <a href="./AdType.md">AdType</a>| This field indicates the subtype of Ad of this instance.| Ignore| Ignore| Ignore |
| url| xsd:string| Destination URL.| Req| ReqUpdatable| Ignore |
| displayUrl| xsd:string| Display URL| Req| ReqUpdatable| Ignore |
| headline| xsd:string| The Title of the ad.| Req| ReqUpdatable| Ignore |
| description| xsd:string| The description of the ad.| Req| Ignore| Ignore |
| AppAd||||||
| description2| xsd:string| The description2 of the ad.| Req| Ignore| Ignore |
| appStore| enum <a href="./AppStore.md">AppStore</a>| The list of Apps ad.| Req| Ignore| Ignore |
| appId| xsd:string| Apps ID or Package name.| Req| Ignore| Ignore |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
