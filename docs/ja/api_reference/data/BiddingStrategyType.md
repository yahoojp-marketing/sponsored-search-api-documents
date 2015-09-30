# BiddingStrategyType (enum)
BiddingStrategyTypeは、入札方法を表します。
### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignService](../services/CampaignService.md)

| 値 | データ型 | 説明 | 
|---|---|---|
| BUDGET_OPTIMIZER| string| 入札価格の上限金額を設定しない自動入札です。 |
| MANUAL_CPC| string| 手動で入札を行います。 |
| PAGE_ONE_PROMOTED| string| 検索結果ページの目標掲載位置です。<br>※キャンペーン、広告グループに適用可能です。 |
| TARGET_ROAS| string| 広告費用対効果の目標値です。<br>※キャンペーン（更新時のみ指定可能）、広告グループに適用可能です。 |
| TARGET_SPEND| string| クリック数を最大化します。<br>※キャンペーン、広告グループに適用可能です。 |
| ENHANCED_CPC| string| コンバージョン数を最大化します。<br>※キャンペーン、広告グループに適用可能です。 |
| TARGET_CPA| string| コンバージョン単価の目標値です。<br>※キャンペーン（更新時のみ指定可能）、広告グループに適用可能です。 |
| NONE| string| 設定した入札設定を取り消して、上位エンティティの入札設定に従う場合に指定します。<br>※広告グループ、キーワードの入札設定を削除する場合に使用します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
