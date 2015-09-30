# TrafficEstimatorSelector
A container to get estimate when you make call.
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| Field | Data Type | Description | 
|---|---|---|
| estimateRequest[]| <a href="../data/EstimateRequest.md">EstimateRequest</a>| The container for estimate request. |
| month| xsd:int| Please specify month for Traffic estimate. Value can be specified between1and 12. <br><br>Month is always considered as a future date. If the request date is January, 2012, and specifies “2,” traffic is estimated for Februry, 2012. If “1” is specified, it will be January, 2013. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
