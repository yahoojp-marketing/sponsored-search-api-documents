# DesktopEstimateResult
DesktopEstimateResult object shows the result of the traffic estimate for the desktop.
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| Field | Data type | Description | 
|---|---|---|
| type| enum <a href="../data/EstimateResultType.md">EstimateResultType</a>| Device type |
| keyword| xsd:string| Keywords |
| matchType| enum <a href="../data/KeywordMatchType.md">KeywordMatchType</a>| Match type |
| bid| xsd:long| Number of bid |
| impressions| xsd:double| Impression estimation |
| clicks| xsd:double| Click estimation |
| rank| xsd:double| Rank estimation |
| cpc| xsd:double| CPC estimation |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
