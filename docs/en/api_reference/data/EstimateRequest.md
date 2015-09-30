# EstimateRequest
Container of estimate request.
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| Field | Data Type | Description | 
|---|---|---|
| target| <a href="../data/EstimateTarget.md">EstimateTarget</a>| Specify target condition required for estimation. |
| keyword| <a href="../data/EstimateKeyword.md">EstimateKeyword</a>| Speciy conditions required for keyword estimation. |
| bid| xsd:long| Bid for estimation. |
| platform[]| <a href="../data/PropPlatformTarget.md">PropPlatformTarget</a>| Device settings.<br>*Can accept only one request |
| wap| enum <a href="../data/Wap.md">Wap</a>| Mobile ads settings |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
