# CampaignEstimateRequest
CampaignEstimateRequestオブジェクトは、見積もりを行うキャンペーンを格納するコンテナです。
### Service
+ [KeywordEstimatorService](../services/KeywordEstimatorService.md)

| フィールド | 必須 | データ型 | 説明 | 
|---|---|---|---|
| campaignId| | xsd:long| キャンペーンIDです。 |
| adGroupEstimateRequests[]| ○| <a href="../data/AdGroupEstimateRequest.md">AdGroupEstimateRequest</a>| 見積もりを行う広告グループを格納するコンテナです。 |
| provinces[]| | xsd:string| 見積もりで使用する広告配信する指定地域（都道府県）です。 |
| dailyBudget| | xsd:long| 見積もりで使用するキャンペーンの一日あたりの予算です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
