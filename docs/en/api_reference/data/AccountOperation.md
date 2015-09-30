# AccountOperation
Account information and transaction for the accounts.
### Service
+ [AccountService](../services/AccountService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| an operator.| Req |
| AccountOperation||||
| operand[]| <a href="../data/Account.md">Account</a>| Account  to operate on.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
