# BudgetOptimizer
BudgetOptimizerオブジェクトは、キャンペーンの自動入札を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| BiddingStrategy(inherited)||||||
| type| enum <a href="./BiddingStrategyType.md">BiddingStrategyType</a>| 入札方法です。| Req| Req| ─ |
| BudgetOptimizerAdGroupBid||||||
| bidCeiling(updatable)| xsd:int| 自動入札設定時の上限入札価格です。※上限入札価格は1円〜9,999円以内で設定してください。なお、上限入札価格を設定しない場合はエラーになります。| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
