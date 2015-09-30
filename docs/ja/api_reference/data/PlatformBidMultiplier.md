# PlatformBidMultiplier
PlatformBidMultiplierオブジェクトは、プラットフォームの入札価格調整率を表します。
### Service
+ [AdGroupBidMultiplierService](../services/AdGroupBidMultiplierService.md)

| フィールド | データ型 | 説明 | SET | 
|---|---|---|---|
| type| enum <a href="./BidMultiplierType.md">BidMultiplierType</a>| 入札価格調整率の種類です。| Req |
| platformName| enum <a href="./PlatformType.md">PlatformType</a>| プラットフォームです。| Req |
| bidMultiplier| xsd:double| 入札価格調整率です。<br>入力可能な値は0か0.10-4.00、または空欄です。小数点2ケタまで入力できます。<br>値が0のときは-100%として扱われ、スマートフォンに配信されません。<br>0.10-4.00のときは-90％から+300%として扱われ、スマートフォンの調整が有効になります。| Optional<br>Updatable |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
