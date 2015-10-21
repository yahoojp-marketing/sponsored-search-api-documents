# AppAd
AppAdオブジェクトは、アプリ向けの広告です。
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
| AppAd|||
| description2| xsd:string| 説明文2です。 |
| appStore| enum <a href="./AppStore_AdGroupAd.md">AppStore</a>| アプリストアです。 <br>※アプリキャンペーンの場合、自動で設定されます|
| appId| string| アプリIDです。<br>※アプリキャンペーンの場合、自動で設定されます |
| devicePreference| enum <a href="../data/DevicePreference.md">DevicePreference</a>| 優先配信デバイスです。<br>※スマートフォンのみ設定可能です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
