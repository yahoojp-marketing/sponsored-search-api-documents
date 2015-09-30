# WebConversion
WebConversionオブジェクトは、ウェブページのコンバージョン測定タグやタグごとのパフォーマンスデータなどのコンバージョントラッカー情報を表します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| フィールド | データ型 | 説明 | ADD | SET | 
|---|---|---|---|---|
| ConversionTracker (inherited)|||||
| WebConversionTracker|||||
| snippet| xsd:string| スニペットです。| -| - |
| markupLanguage| enum <a href="../data/MarkupLanguage.md">MarkupLanguage</a>| マークアップランゲージです。<br>※電話コンバージョンの場合は、HTMLのみ指定可能です。| Req| Opt |
| httpProtocol| enum <a href="../data/HttpProtocol.md">HttpProtocol</a>| httpプロトコルです。| Req| Opt |
| trackingCodeType| enum <a href="./TrackingCodeType.md">TrackingCodeType</a>| トラッキングコードタイプです。| Req| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
