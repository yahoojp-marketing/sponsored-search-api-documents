# TotalEstimateResult
TotalEstimateResultオブジェクトは、全デバイスのトラフィック予測情報を格納します。
### Service
+ [TrafficEstimatorService](../services/TrafficEstimatorService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| type| enum <a href="../data/EstimateResultType.md">EstimateResultType</a>| デバイス種類です。 |
| keyword| xsd:string| キーワードです。 |
| matchType| enum <a href="../data/KeywordMatchType.md">KeywordMatchType</a>| マッチタイプを示します。 |
| carrier| enum <a href="../data/CarrierName.md">CarrierName</a>| 配信キャリアを示します。 |
| bid| xsd:long| 入札単価です。 |
| impressions| xsd:double| 予測インプレッション数です。 |
| clicks| xsd:double| 予測クリック数です。 |
| rank| xsd:double| 予測掲載順位です。 |
| cpc| xsd:double| 予測CPCです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
