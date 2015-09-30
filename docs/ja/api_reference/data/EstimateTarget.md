# EstimateTarget
EstimateTargetオブジェクトは、見積もりのターゲット設定を格納するコンテナです。
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| network| enum <a href="../data/EstimateNetwork.md">EstimateNetwork</a>| 広告配信ネットワークを指定します。 |
| mobileCarrier| enum <a href="../data/CarrierName.md">CarrierName</a>| キャリア名を指定します。 |
| province[]| xsd:string| 配信対象の都道府県を指定します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
