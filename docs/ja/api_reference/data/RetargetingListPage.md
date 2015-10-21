# RetargetingListPage
RetargetingListPageは、ターゲットリストのgetメソッドの実行結果（全Entityのリスト）を保持するオブジェクトです。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| Page(inherited)|||||||||
| totalNumEntries| xsd:int||||||| 取得される項目の総件数です。 |
| Page.Type| xsd:string||||||| このインスタンスのPageのサブタイプです。 |
| RetargetingListPage|||||||
| values[]| <a href="./RetargetingListValues.md">RetargetingListValues</a>| unbounded| 0| ○| -| -| -| getメソッドの実行結果です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

