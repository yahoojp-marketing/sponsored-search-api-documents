# AdGroupCriterion
AdGroupCriterionオブジェクトは、広告グループのクライテリアを表します。
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignId| xsd:long| キャンペーンIDです。 |
| campaignName| xsd:string| キャンペーン名です。 |
| adGroupId| xsd:long| 広告グループIDです。 |
| adGroupName| xsd:string| 広告グループ名です。 |
| criterionUse| enum <a href="../data/CriterionUse.md">CriterionUse</a>| クライテリアを単価設定可能にするか除外にするかを選択します。 |
| criterion| <a href="../data/Criterion.md">Criterion</a><br>inherited <a href="../data/Keyword.md">Keyword</a>|広告グループのクライテリアです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
