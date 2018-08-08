# LocationTarget
LocationTarget object is a location target setting.
### Service
+ [CampaignTargetService](../../services/CampaignTargetService.md)

### Namespace
[CampaignTargetService#Namespace](../../services/CampaignTargetService.md#namespace)

| Field | Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Target (inherited)||||||
| targetId| xsd:string| Target ID| Req| Req| Req |
| type| enum <a href="TargetType.md">TargetType</a>| Target Type| Req| Req| Req |
| LocationTarget||||||
| provinceNameEN| xsd:string| Prefecture（English）| Ignore| Ignore| Ignore |
| cityNameEN| xsd:string| City （English）| Ignore| Ignore| Ignore |
| provinceNameJA| xsd:string| Prefecture（Japanese）| Ignore| Ignore| Ignore |
| cityNameJA| xsd:string| City （Japanese）| Ignore| Ignore| Ignore |
| excludedType| enum <a href="ExcludedType.md">ExcludedType</a>| Included or Excluded| Opt| Ignore| Ignore |
| targetingStatus| enum <a href="TargetingStatus.md">TargetingStatus</a>| Status of Targeting| Ignore| Ignore| Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
