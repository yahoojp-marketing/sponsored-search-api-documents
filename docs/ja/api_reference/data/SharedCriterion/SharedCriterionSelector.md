# SharedCriterionSelector
SharedCriterionSelectorオブジェクトは、getメソッドの検索条件を保持します。
### Service
+ [SharedCriterionService](../../services/SharedCriterionService.md)

### Namespace
[SharedCriterionService#Namespace](../../services/SharedCriterionService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountIds| xsd: long| アカウントIDです。 |
| sharedListIds[0..20]| xsd: long| 共有リストのIDです。 |
| criterionIds[0..1000]| xsd: long| クライテリオンのIDです。 |
| paging| <a href="../Common/Paging.md">Paging</a>| ページの取得範囲です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

