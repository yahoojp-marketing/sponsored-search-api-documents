# AccountSelector
AccountSelectorオブジェクトは、選択するアカウントを表します。
### Service
+ [AccountService](../services/AccountService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountIds[]| xsd: long| アカウントIDの配列です。各配列には、アカウントIDが含まれます。指定しない場合は、APIアカウントIDでアクセス可能なアカウント全てが含まれます。アプリケーションアカウントを用いた代行認証の場合は、アカウントIDの指定が必須です。 |
| accountTypes[]| enum <a href="../data/AccountType.md">AccountType</a>| アカウントの料金支払い種別です。 |
| accountStatuses[]| enum <a href="../data/AccountStatus.md">AccountStatus</a>| アカウントの契約状況です。 |
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
