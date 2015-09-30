# MobileAd
Mobile ad excluding for smartphone.
*mutate(ADD) and mutate(SET) are unavailable due to the closing of mobile (feature phone) ads.
　get and mutate(REMOVE) are still available to use.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Ad(inherited)||||||
| type| enum <a href="./AdType.md">AdType</a>| This field indicates the subtype of Ad of this instance.| Ignore| Ignore| Ignore |
| url| xsd:string| Destination URL.| Req| ReqUpdatable| Ignore |
| displayUrl| xsd:string| Display URL| Req| ReqUpdatable| Ignore |
| headline| xsd:string| The Title of the ad.| Req| ReqUpdatable| Ignore |
| description| xsd:string| The description of the ad.| Req| ReqUpdatable| Ignore |
| MobileAd||||||
| markupLanguages| enum <a href="./MarkupLanguageType.md">MarkupLanguageType</a>| The list of markup languages to use for the mobile ad.| Req| ReqUpdatable| Ignore |
| mobileCarriers[]| enum <a href="./CarrierName.md">CarrierName</a>| The list of mobile carriers to use for the mobile ad.| Req| ReqUpdatable| Ignore |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
