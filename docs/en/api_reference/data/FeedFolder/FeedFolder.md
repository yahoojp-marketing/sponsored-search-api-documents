# FeedFolder
FeedFolder object is the list of Data elements on auto data insertion.

### Service
+ [FeedFolderService](../../services/FeedFolderService.md)

### Namespace
[FeedFolderService#Namespace](../../services/FeedFolderService.md#namespace)

| Field | Data Type |  response | add | set | remove | Description |
|---|---|---|---|---|---|---|
| accountId| long| yes| Ignore| Ignore| Ignore| Account ID.<br>*Not required by design change on editorials. |
| feedFolderId| long| yes| Ignore| Requirement<br>Not updatable| Requirement<br>Not updatable| Feed Folder ID |
| feedFolderTrackId| long|  yes| Ignore| Ignore| Ignore| Tracking ID of Feed folder. |
| feedFolderName| string| yes| Requirement| Ignore| Ignore| List name of Feed folder. |
| feedAttribute[]| <a href="FeedAttribute.md">FeedAttribute</a>| yes| Optional| Optional| Ignore| Feed attribute |
| placeholderType| enum <a href="FeedFolderPlaceholderType.md">FeedFolderPlaceholderType</a>| yes| Requirement| Ignore| Ignore| Type of FeedItem. |
| domain| string| yes| Optional| Ignore| Ignore| Domain. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
