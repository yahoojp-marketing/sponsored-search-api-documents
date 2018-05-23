# AccountSharedSelector
AccountSharedSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

### Service
+ [AccountSharedService](../../services/AccountSharedService.md)

### Namespace
[AccountSharedService#Namespace](../../services/AccountSharedService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| sharedListIds[0..20] | xsd:long | 検索対象外キーワードリストIDです。 |
| paging| <a href="../Common/Paging.md">Paging</a>| ページの取得範囲です。|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

