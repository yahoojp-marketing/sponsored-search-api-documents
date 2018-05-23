# AccountShared
AccountShared object holds search results (all entities list) of get method.

### Service
+ [AccountSharedService](../../services/AccountSharedService.md)

### Namespace
[AccountSharedService#Namespace](../../services/AccountSharedService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|
| accountId | long | Account ID. | Yes | - | - | - | - |
| sharedListId | long | Negative keyword list ID. | Yes | - | - | Requirement<br>NotUpdatable | Requirement |
| name | string | Negative keyword list name. | Yes | - | Requirement | Requirement<br>Updatable | - |
| memberCount | integer | Number of items on Negative keyword list (keyword excluded on search).| Yes | - | - | - | - |
| referenceCount | integer | Number of campaigns which use negative keyword list.| Yes | - | - | - | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
