# TextAd2
TextAd2オブジェクトは、スポンサードサーチのPCおよびスマートフォン向けの広告を表します。
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| Ad(inherited)|||
| type| enum <a href="./AdType.md">AdType</a>| 広告タイプです。 |
| url| xsd:string| リンク先URLです。 |
| displayUrl| xsd:string| 表示URLです。 |
| headline| xsd:string| タイトルです。 |
| description| xsd:string| 説明文（1行目）です。 |
| TextAd2|||
| description2| xsd:string| 説明文（2行目）2です。 |
| devicePreference| enum <a href="./DevicePreference.md">DevicePreference</a>| 広告を優先的に配信するデバイスを指定頂けます。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
