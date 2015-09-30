# FeedFolder
FeedFolder is the elements of list of Data auto insertion.
### Service
+ [FeedFolderService](../services/FeedFolderService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| yes| Ignore| Ignore| Ignore| Account ID |
| feedFolderId| long| 1| 0| yes| Ignore| IgnoreNot updatable| IgnoreNot updatable| Feed Folder ID |
| feedFolderName| string| 1| 0| yes| Requirement| Ignore| Ignore| Data auto insertion name |
| feedAttribute[]| <a href="./FeedAttribute.md">FeedAttribute</a>| 20| 0| yes| Requirement| Requirement| Ignore| Feed attribute |
| placeholderType| enum <a href="./PlaceholderType_FeedFolder.md">PlaceholderType</a>| 1| 1| yes| Ignore| Ignore| Ignore| Type of Data auto insertion information |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
