# FeedFolder
FeedFolderオブジェクトは、自動データ挿入のリストを格納します。
### Service
+ [FeedFolderService](../services/FeedFolderService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Ignore| Ignore| Ignore| アカウントIDです。<br>※入稿の仕様変更により不要になりました。 |
| feedFolderId| long| 1| 0| ○| Ignore| RequirementNot updatable| RequirementNot updatable| FeedフォルダIDです。 |
| feedFolderName| string| 1| 0| ○| Requirement| Ignore| Ignore| Feedフォルダのリスト名です。 |
| feedAttribute[]| <a href="./FeedAttribute.md">FeedAttribute</a>| 20| 0| ○| Requirement| Requirement| Ignore| Feedの属性（カラム）情報です。 |
| placeholderType| enum <a href="./PlaceholderType_FeedFolder.md">PlaceholderType</a>| 1| 1| ○| Ignore| Ignore| Ignore| FeedItemの種類です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
