# Budget
Budgetオブジェクトは、キャンペーン予算に関する情報を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | ADD | SET | 
|---|---|---|---|---|
| Period(updatable)| enum <a href="../data/BudgetPeriod.md">BudgetPeriod</a>| 予算の設定期間です。| Req| Opt |
| Amount(updatable)| xsd:long| キャンペーン予算の利用金額（1日単位）です。| Req| Opt |
| deliveryMethod(updatable)| enum <a href="../data/BudgetDeliveryMethod.md">BudgetDeliveryMethod</a>| 広告の配信方法です。| Opt| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
