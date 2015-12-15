# NegativeCampaignCriterion
NegativeCampaignCriterionオブジェクトは、キャンペーンの除外クライテリアを表します。

### Service
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

| フィールド | データ型 | 説明 | ADD | REMOVE | 
|---|---|---|---|---|
| CampaignCriterion(inherited)|||||
| accountId| xsd:long| アカウントIDです。| Req| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req| Req |
| campaignName| xsd:string| キャンペーン名です。| ─| ─ |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| クライテリアを単価設定可能にするか除外にするかを選択します。| Req| Req |
| criterion| <a href="./Criterion_CampaignCriterion.md">Criterion</a><br>inherited <a href="./Keyword_CampaignCriterion.md">Keyword</a>| クライテリアです。| Req| Req |
| NegativeCampaignCriterion|||||

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
