# MobileAd
MobileAdオブジェクトは、スマートフォン以外の携帯電話向けの広告です。<br>
※モバイル向けサービスの提供終了により、mutate(ADD)とmutate(SET)による入稿はご利用いただけません。<br>
　なお、getによる取得やmutate(REMOVE)による削除は引き続きご利用いただけます。
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| Ad(inherited)|||
| type| enum <a href="./AdType.md">AdType</a>| 広告のタイプです。 |
| url| xsd:string| リンク先URLです。 |
| displayUrl| xsd:string| 表示URLです。 |
| headline| xsd:string| タイトル文です。 |
| description| xsd:string| 説明文です。 |
| MobileAd|||
| markupLanguages| enum <a href="./MarkupLanguageType.md">MarkupLanguageType</a>| マークアップ言語です。 |
| mobileCarriers[]| enum <a href="./CarrierName.md">CarrierName</a>| モバイルキャリアです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
