# TrafficEstimatorSelector
TrafficEstimatorSelectorオブジェクトは、見積もりのリクエストを格納するコンテナです。
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| estimateRequest[]| <a href="../data/EstimateRequest.md">EstimateRequest</a>| 見積もりのリクエストのコンテナです。 |
| month| xsd:int| トラフィックを見積りの対象月を指定します。<br>値は1から12です。<br>monthは常に未来の日付として解釈されます。<br>例えば、リクエスト日が2012年1月の場合、「2」を指定すると2012年02月の見積りとなり、<br>「1」を指定した場合は2013年1月の見積りとなります。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
