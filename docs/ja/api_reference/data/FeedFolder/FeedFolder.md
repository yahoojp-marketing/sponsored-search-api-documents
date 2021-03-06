# FeedFolder
FeedFolderオブジェクトは、自動データ挿入のリストを格納します。

### Service
+ [FeedFolderService](../../services/FeedFolderService.md)

### Namespace
[FeedFolderService#Namespace](../../services/FeedFolderService.md#namespace)

| フィールド | データ型 |  response | add | set | remove | 説明 |
|---|---|---|---|---|---|---|
| accountId| xsd:long|  yes| Ignore| Ignore| Ignore| アカウントIDです。<br>※入稿の仕様変更により不要になりました。 |
| feedFolderId| xsd:long|  yes| Ignore| Requirement<br>Not updatable| Requirement<br>Not updatable| FeedフォルダIDです。 |
| feedFolderTrackId| xsd:long|  yes| Ignore| Ignore| Ignore| Feedフォルダのトラッキング用IDです。 |
| feedFolderName| xsd:string| yes| Requirement| Ignore| Ignore| Feedフォルダのリスト名です。 |
| feedAttribute[]| <a href="FeedAttribute.md">FeedAttribute</a>| yes| Optional| Optional| Ignore| Feedの属性（カラム）情報です。 |
| placeholderType| enum <a href="FeedFolderPlaceholderType.md">FeedFolderPlaceholderType</a>| yes| Requirement| Ignore| Ignore| FeedItemの種類です。 |
| domain| xsd:string| yes| Optional| Ignore| Ignore| ドメインです。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
