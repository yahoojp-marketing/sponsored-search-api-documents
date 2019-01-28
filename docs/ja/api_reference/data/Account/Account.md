# Account
Accountオブジェクトは、アカウントを表します。

### Service
+ [AccountService](../../services/AccountService.md)

### Namespace
[AccountService#Namespace](../../services/AccountService.md#namespace)

| フィールド | データ型 | 説明 | SET |
|---|---|---|---|
| accountid(notupdatable)| xsd:long| アカウントID| Req |
| accountName(updatable)| xsd:string| アカウント名| Opt |
| accountType| enum <a href="AccountType.md">AccountType</a>| 料金の支払い方法| ─ |
| accountStatus| enum <a href="AccountStatus.md">AccountStatus</a>| アカウントの契約状況| ─ |
| deliveryStatus(updatable)| enum <a href="DeliveryStatus.md">DeliveryStatus</a>| 広告の配信状況| Opt |
| budget| <a href="AccountBudget.md">AccountBudget</a>| アカウントの広告予算| ─ |
| autoTaggingEnabled(updatable)| enum <a href="AutoTaggingEnabled.md">AutoTaggingEnabled</a>| 自動タグ設定の管理フラグ| Opt<br>default: FALSE |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
