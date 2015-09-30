# PageOnePromotedBiddingScheme [Non-BiddingStrategyService]
PageOnePromotedBiddingSchemeオブジェクトは、検索結果ページの目標掲載位置の自動入札設定情報を表します。
（BiddingStrategyService以外用のオブジェクトです。）
### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| BiddingSchema(inherited)||||||
| biddingStrategyType| enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a>| 自動入札タイプです。| ─| ─| ─ |
| PageOnePromotedBiddingScheme||||||
| targetPositionType| enum <a href="../data/TargetPositionType.md">TargetPositionType</a>| 掲載場所です。| ─| ─| ─ |
| bidCeiling| xsd:long| 入札価格の上限です。（0?50000）<br>※「0」が設定された場合、上限設定はありません。| ─| ─| ─ |
| bidMultiplier| xsd:double| 入札価格調整率です。<br>※0.10 〜10.00（-90%〜+900%）の範囲内のみ許容します。| ─| ─| ─ |
| bidChangesForRaisesOnly| enum <a href="../data/BidChangesForRaisesOnly.md">BidChangesForRaisesOnly</a>| 入札価格の自動・手動設定です。| ─| ─| ─ |
| raiseBidWhenBudgetConstrained| enum <a href="../data/RaiseBidWhenBudgetConstrained.md">RaiseBidWhenBudgetConstrained</a>| 予算消化による広告掲載機会制限時の入札価格の引き上げ設定です。| ─| ─| ─ |
| raiseBidWhenLowQualityScore| enum <a href="../data/RaiseBidWhenLowQualityScore.md">RaiseBidWhenLowQualityScore</a>| 品質の低いキーワードに対する入札価格の引き上げ設定です。| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
