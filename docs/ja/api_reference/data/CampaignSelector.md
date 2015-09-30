# CampaignSelector
CampaignSelectorオブジェクトは、操作の対象とするキャンペーンの情報およびフィルタ条件を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| -| -| - |
| campaignIds[]| xsd:long| キャンペーンIDです。指定しない場合は、フィルタ条件にすべてのキャンペーンが含まれます。| -| -| - |
| userStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| ユーザーにより設定される広告の掲載状況です。指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。| -| -| - |
| biddingStrategyIds[]| xsd:long| 自動入札IDです。| -| -| - |
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。| -| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
