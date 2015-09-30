# AdGroupEstimateRequest
AdGroupEstimateRequestオブジェクトは、見積もりを行う広告グループを格納するコンテナです。
### Service
+ [KeywordEstimatorService](../services/KeywordEstimatorService.md)

| フィールド | 必須 | データ型 | 説明 | 
|---|---|---|---|
| adGroupId| | xsd:long| 広告グループIDです。 |
| keywordEstimateRequests| ○| <a href="../data/KeywordEstimateRequest.md">KeywordEstimateRequest</a>| 見積もりを行うキーワードのコンテナです。 |
| maxCpc| | xsd:long| 広告グループの見積もりに使用する上限クリック単価です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
