# AdGroupSelector
AdGroupSelectorオブジェクトは、指定された広告グループを表します。
### Service
+ [AdGroupService](../services/AdGroupService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignIds[]| xsd:long| キャンペーンIDです。<br>指定しない場合は、フィルタ条件にすべてのキャンペーンが含まれます。 |
| adGroupIds[]| xsd:long| 広告グループIDの配列です。<br>指定しない場合は、キャンペーンID以下のすべての広告グループが含まれます。 |
| userStatuses[]| enum <a href="../data/DeliveryStatus.md">DeliveryStatus</a>| ユーザーにより設定される広告の掲載状況です。<br>指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。 |
| biddingStrategyIds[]| xsd:long| 自動入札IDです。 |
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
