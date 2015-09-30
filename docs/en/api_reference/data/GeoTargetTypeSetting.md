# GeoTargetTypeSetting
GeoTargetTypeSettings object is a container for GeoTargeting.
### Service
+ [CampaignService](../services/CampaignService.md)

| Field | Data Type | Description | ADD | SET | 
|---|---|---|---|---|
| type| enum <a href="./SettingType.md">SettingType</a>| GeoTarget type| Req| Req |
| positiveGeoTargetType| enum <a href="./GeoTargetType.md">GeoTargetType</a>| GeoTargetsetting for Campaign| Opt(default:DON'T_CARE)| OptUpdatable |
| negativeGeoTargetType| enum <a href="./GeoTargetType.md">GeoTargetType</a>| Negative GeoTarget setting for Campaign.| Opt(default:DONT_CARE)| OptUpdatable |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
