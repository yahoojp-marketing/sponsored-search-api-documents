# LocationTarget
LocationTargetオブジェクトは、地域ターゲティング設定です。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Target (inherited)||||||
| targetId| xsd:string| ターゲットIDです。| Req| Req| Req |
| type| enum <a href="./TargetType.md">TargetType</a>| ターゲットタイプです。| Req| Req| Req |
| LocationTarget||||||
| provinceNameEN| xsd:string| 都道府県名（英語）です。| -| -| - |
| cityNameEN| xsd:string| 市区町村名（英語）です。| -| -| - |
| provinceNameJA| xsd:string| 都道府県名（日本語）です。| -| -| - |
| cityNameJA| xsd:string| 市区町村名（日本語）です。| -| -| - |
| excludedType| enum <a href="./ExcludedType.md">ExcludedType</a>| 包含または除外| Opt| -| - |
| targetingStatus| enum <a href="./TargetingStatus.md">TargetingStatus</a>| ターゲティングステータスです。| -| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
