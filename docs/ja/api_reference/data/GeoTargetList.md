# GeoTargetList
GeoTargetListオブジェクトは、地域設定を表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | SET | 
|---|---|---|---|
| TargetList(inherited)||||
| accountId| xsd:long| アカウントIDです。| Req |
| campaignId(notupdatable)| xsd:long| キャンペーンIDです。| Req |
| type(notupdatable)| enum <a href="./TargetType.md">TargetType</a>| ターゲティング設定です。| Req |
| GeoTargetList||||
| targets[]| <a href="./GeoTarget.md">GeoTarget</a><br>inherited <a href="./ProvinceTarget.md">ProvinceTarget</a>| 地域設定です。|  |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
