# BiddingStrategy [AdGroupService]
BiddingStrategyオブジェクトは、入札方法を表します。（AdGroupService用のオブジェクトです。）
### Service
+ [AdGroupService](../services/AdGroupService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| biddingStrategyId| xsd:long| 自動入札IDです。| Opt| Opt<br>                        (updatable)| ─ |
| biddingStrategyName| xsd:string| 自動入札名です。（50文字以内になります）| ─| ─| ─ |
| biddingStrategyType| enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a>| 自動入札タイプです。| Opt| Opt<br>                        (updatable)| ─ |
| biddingStrategySource| enum <a href="../data/BiddingStrategySource.md">BiddingStrategySource</a>| 入札ソースです。| ─| ─| ─ |
| biddingScheme| <a href="../data/BiddingScheme_nonBiddingStrategy.md">BiddingScheme</a><br><br> inherited <a href="../data/ManualCpcBiddingScheme.md">ManualCpcBiddingScheme</a><br><br> inherited <a href="../data/BudgetOptimizerBiddingScheme.md">BudgetOptimizerBiddingScheme </a><br><br> inherited <a href="../data/EnhancedCpcBiddingScheme_nonBiddingStrategy.md">EnhancedCpcBiddingScheme</a><br><br> inherited <a href="../data/PageOnePromotedBiddingScheme_nonBiddingStrategy.md">PageOnePromotedBiddingScheme </a><br><br> inherited <a href="../data/TargetCpaBiddingScheme_nonBiddingStrategy.md">TargetCpaBiddingScheme</a><br><br> inherited <a href="../data/TargetSpendBiddingScheme_nonBiddingStrategy.md">TargetSpendBiddingScheme</a><br><br> inherited <a href="../data/TargetRoasBiddingScheme_nonBiddingStrategy.md">TargetRoasBiddingScheme</a>| 自動入札設定詳細です。| ─| ─| ─ |
| initialBid| enum <a href="../data/Bid_AdGroup.md">Bid</a>| 入札価格です。| Opt| Opt<br>                        (updatable)| ─ |
| parentBiddingStrategyConfigurations[]| enum <a href="../data/BiddingStrategy_AdGroup.md">BiddingStrategy</a>| 上位エンティティの入札設定です。| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
