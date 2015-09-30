# Account
Accountオブジェクトは、アカウントを表します。
### Service
+ [AccountService](../services/AccountService.md)

| フィールド | データ型 | 説明 | SET | 
|---|---|---|---|
| accountid(notupdatable)| xsd:long| アカウントIDです。| Req |
| accountName(updatable)| xsd:string| アカウント名です。| Opt |
| accountType| enum <a href="../data/AccountType.md">AccountType</a>| 料金の支払い方法です。| ─ |
| accountStatus| enum <a href="../data/AccountStatus.md">AccountStatus</a>| アカウントの契約状況です。| ─ |
| deliveryStatus(updatable)| enum <a href="../data/DeliveryStatus.md">DeliveryStatus</a>| 広告の配信状況です。| Opt |
| budget| <a href="../data/AccountBudget.md">AccountBudget</a>| アカウントの広告予算です。| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
