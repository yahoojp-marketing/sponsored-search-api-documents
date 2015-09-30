# CampaignOperation
CampaignOperationオブジェクトは、操作の対象となるキャンペーンの情報と処理の内容を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| 処理を表す演算子です。| Req |
| CampaignOperation||||
| accountId| xsd:long| アカウントIDです。| Req |
| operand[]| <a href="./Campaign.md">Campaign</a>| Campaignオブジェクトの配列です。各配列には処理の対象となるキャンペーンの情報が含まれます。| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
