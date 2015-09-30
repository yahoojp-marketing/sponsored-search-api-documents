# FeedAttribute
FeedAttributeオブジェクトは、自動データ挿入のリストの属性を格納します。
### Service
+ [FeedFolderService](../services/FeedFolderService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| feedAttributeId| long| 1| 0| ○| Ignore| Ignore| Ignore| 自動データ挿入のリストの属性（カラム）IDです。 |
| feedAttributeName| string| 1| 0| ○| Requirement| Requirement| Ignore| 自動データ挿入のリストの属性（カラム）名です。 |
| placeholderField| enum <a href="./PlaceholderField_FeedFolder.md">PlaceholderField</a>| 1| 0| ○| Requirement| Requirement| Ignore| FeedItem情報です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
