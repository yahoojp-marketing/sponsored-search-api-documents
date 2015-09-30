# NegativeAdGroupCriterion
NegativeAdGroupCriterionオブジェクトは、広告グループの除外クライテリアを表します。
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| フィールド | データ型 | 説明 | ADD | REMOVE | 
|---|---|---|---|---|
| AdGroupCriterion(inherited)|||||
| accountId| xsd:long| アカウントIDです。| Req| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req| Req |
| campaignName| xsd:string| キャンペーン名です。| ─| ─ |
| adGroupId| xsd:long| 広告グループIDです。| Req| Req |
| adGroupName| xsd:string| 広告グループ名です。| ─| ─ |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| クライテリアを単価設定可能にするか除外にするかを選択します。| Req| ─ |
| criterion| <a href="./Criterion.md">Criterion</a><br>inherited <a href="./Keyword.md">Keyword</a>| クライテリアです。| Req| Req |
| NegativeAdGroupCriterion|||||
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
