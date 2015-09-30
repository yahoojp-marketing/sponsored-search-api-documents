# ProvinceTarget
ProvinceTargetオブジェクトは、地域設定を表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | SET | 
|---|---|---|---|
| GeoTarget(inherited)||||
| type(updatable)| enum <a href="./TargetType.md">TargetType</a>| ターゲティング設定です。| Req |
| excluded| enum <a href="./GeoExcludedType.md">GeoExcludedType</a>| 地域ターゲティング設定での地域の包含または除外を示します。| Opt |
| ProvinceTarget||||
| provinceCode(updatable)| xsd:string| 都道府県コードです。| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
