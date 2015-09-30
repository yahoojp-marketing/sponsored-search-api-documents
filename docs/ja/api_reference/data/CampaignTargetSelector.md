# CampaignTargetSelector
CampaignTargetSelectorオブジェクトは、操作の対象とするキャンペーンのターゲティング設定を表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignIds[]| xsd:long| キャンペーンIDです。 |
| targetIds[]| xsd:string| ターゲットIDです。 |
| targetTypes[]| enum <a href="./TargetType.md">TargetType</a>| ターゲットタイプです。 |
| ExcludedType| enum <a href="./ExcludedType.md">ExcludedType</a>| 包含または除外の指定です。 |
| paging| <a href="./Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
