# AccountSelector
Explains which accounts to return.
### Service
+ [AccountService](../../services/AccountService.md)

### Namespace
[AccountService#Namespace](../../services/AccountService.md#namespace)

| Field | Data Type | Description |
|---|---|---|
| accountIds[]| xsd: long| It is the arrangement of account ID. Account ID is contained in each arrangement. When not specifying, all account that can be accessed by API account ID is included. |
| accountTypes[]| enum <a href="AccountType.md">AccountType</a>| Payment Type. |
| accountStatuses[]| enum <a href="AccountStatus.md">AccountStatus</a>| Account Contract Status. |
| paging| <a href="../Common/Paging.md">Paging</a>| The page that is returned as a page. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
