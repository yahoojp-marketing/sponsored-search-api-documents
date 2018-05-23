# GeographicLocation
GeographicLocationオブジェクトは、地域情報を格納します。
### Service
+ [DictionaryService](../../services/DictionaryService.md)

### Namespace
[DictionaryService#Namespace](../../services/DictionaryService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| code| xsd:string| 地域コードです。 |
| parent| xsd:string| 上位地域コードです。 |
| name| xsd:string| 地域名(市区町村のみ)です。 |
| fullName| xsd:string| 地域名(都道府県名からすべて)です。 |
| order| xsd:string| 並び順です。<br>下記の順序に基づいた連番となります。<br>都道府県は北海道、青森、・・・・沖縄の順<br>都道府県配下の市区町村は五十音順 |
| status| enum <a href="GeographicLocationStatus.md">GeographicLocationStatus</a>| 対象地域のステータスです。 |
| child| <a href="GeographicLocation.md">GeographicLocation</a>| 下位の地域構造です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
