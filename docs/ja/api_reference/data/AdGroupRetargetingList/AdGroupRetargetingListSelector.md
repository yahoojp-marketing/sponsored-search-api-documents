# AdGroupRetargetingListSelector
AdGroupRetargetingListSelector、広告グループレベルでのターゲットリスト設定のgetメソッド検索条件（実行パラメータ）を保持するオブジェクトです。

### Service
+ [AdGroupRetargetingListService](../../services/AdGroupRetargetingListService.md)

### Namespace
[AdGroupRetargetingListService#Namespace](../../services/AdGroupRetargetingListService.md#namespace)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 |
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| -| -| -| -| 検索条件：アカウントIDです。 |
| campaignIds[]| long| unbounded| 0| -| -| -| -| 検索条件：キャンペーンIDです。 |
| targetListIds[]| long| unbounded| 0| -| -| -| -| 検索条件：ターゲットリストIDです。 |
| adGroupIds[]| long| unbounded| 0| -| -| -| -| 検索条件：広告グループIDです。 |
| excludedType[]| enum <a href="ExcludedType.md">ExcludedType</a>| 1| 0| -| -| -| -| 検索条件：包含/除外です。|
| paging| <a href="../Common/Paging.md">Paging</a>| 1| 0| -| -| -| -| 検索条件：取得範囲です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
