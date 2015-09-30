# TargetRoasBiddingScheme [Non-BiddingStrategyService]
TargetRoasBiddingSchemeオブジェクトは、広告費用対効果の目標値の自動入札設定情報を表します。
（BiddingStrategyService以外用のオブジェクトです。）
### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| BiddingSchema(inherited)||||||
| biddingStrategyType| enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a>| 自動入札タイプです。| Req| Req<br>                        (notupdatable)| ─ |
| TargetRoasBiddingScheme||||||
| targetRoas| xsd:double| 広告費用対効果の目標値<br>※0.01 〜1000.00（1%〜100000%）の範囲内のみ許容します。<br>※Return On Advertising Spend(ROAS)| ─| ─| ─ |
| bidCeiling| xsd:long| 入札価格の上限です。（0?50000）<br>※「0」が設定された場合、上限設定はありません。| ─| ─| ─ |
| bidFloor| xsd:long| 入札価格の下限です。<br>※ 設定を解除する場合は「0」を指定します。| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
