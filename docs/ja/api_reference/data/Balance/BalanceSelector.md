# BalanceSelector
BalanceSelectorオブジェクトは、アカウント残高を取得するアカウントを示します。
### Service
+ [BalanceService](../../services/BalanceService.md)

### Namespace
[BalanceService#Namespace](../../services/BalanceService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountIds[]| xsd:long| アカウントIDの配列です。指定しない場合は、APIアカウントIDでアクセス可能なアカウント全てが含まれます。アプリケーションアカウントを用いた代行アクセスの場合は、必ずアカウントIDを指定してください。 |
| paging| <a href="../Common/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
