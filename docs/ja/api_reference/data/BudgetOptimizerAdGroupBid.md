# BudgetOptimizerAdGroupBid
BudgetOptimizerAdGroupBidオブジェクトは、広告グループの最高入札価格を表しますが、
BiddingStrategyTypeがBUDGET_OPTIMIZERの場合この値は無視され、入札価格の上限金額を設定しない自動入札機能が有効になります。
### Service
+ [AdGroupService](../services/AdGroupService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| AdGroupBid(inherited)||||||
| type| enum <a href="./BiddingStrategyType.md">BiddingStrategyType</a>| 入札方法です。| ─| ─| ─ |
| BudgetOptimizerAdGroupBid||||||
| KeywordMaxCpc(updatable)| xsd:long| 広告グループの最高入札価格です。| Opt(default: 1)| Opt| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
