# FeedItemSelector
FeedItemSelectorオブジェクトは、Feedアイテムの情報を指定します。
### Service
+ [FeedItemService](../services/FeedItemService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| feedItemIds[]| xsd:long| FeedアイテムIDです。 |
| placeholderTypes[]| enum <a href="../data/PlaceholderType.md">PlaceholderType</a>| Feedアイテムのタイプです。 |
| approvalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| 審査ステータスです。 |
| paging| <a href="../data/Paging.md">Paging</a>| ページング設定です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
