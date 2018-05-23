# Account
Sponsored Search API Account
### Service
+ [AccountService](../../services/AccountService.md)

### Namespace
[AccountService#Namespace](../../services/AccountService.md#namespace)

| Field | Data Type | Description | Restrictions |
|---|---|---|---|
| accountId| xsd:long| Account ID.| Req |
| accountName| xsd:string| Account Name.| Opt |
| accountType| enum <a href="AccountType.md">AccountType</a>| Payment method.| ─ |
| accountStatus| enum <a href="AccountStatus.md">AccountStatus</a>| Status of account signup| ─ |
| deliveryStatus| enum <a href="DeliveryStatus.md">DeliveryStatus</a>| Serving Status| Opt |
| budget| <a href="AccountBudget.md">AccountBudget</a>| Budget| ─ |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
