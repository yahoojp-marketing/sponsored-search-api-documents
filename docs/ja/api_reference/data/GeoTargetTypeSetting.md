# GeoTargetTypeSetting
GeoTargetTypeSettingsオブジェクトは、地域ターゲットの情報を格納するコンテナです。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | ADD | SET | 
|---|---|---|---|---|
| type| enum <a href="./SettingType.md">SettingType</a>| 地域ターゲットのタイプです。| Req| Req |
| positiveGeoTargetType| enum <a href="./GeoTargetType.md">GeoTargetType</a>| キャンペーンで使用するターゲット地域の設定です。| Opt(default:DONT_CARE)| OptUpdatable |
| negativeGeoTargetType| enum <a href="./GeoTargetType.md">GeoTargetType</a>| キャンペーンで使用する除外地域の設定です。| Opt(default:LOCATION_OF_PRESENCE)| OptUpdatable |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
