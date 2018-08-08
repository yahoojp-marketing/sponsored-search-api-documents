# FeedFolderSelector
FeedFolderSelectorオブジェクトは、自動データ挿入のリストの基本情報を格納します。
### Service
+ [FeedFolderService](../../services/FeedFolderService.md)

### Namespace
[FeedFolderService#Namespace](../../services/FeedFolderService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| feedFolderIds[]| xsd:long| 自動データ挿入のリストのIDです。 |
| placeholderTypes[]| enum [FeedFolderPlaceholderType](./FeedFolderPlaceholderType.md) | プレイスホルダータイプです。 |
| paging|<a href="../Common/Paging.md">Paging</a>| ページング設定です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
