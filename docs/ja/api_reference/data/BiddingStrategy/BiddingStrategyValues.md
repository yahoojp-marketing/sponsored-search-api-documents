# BiddingStrategyValues
BiddingStrategyValuesオブジェクトは、自動入札設定の実行をしたときの結果に関する情報を表します。

### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE |
|---|---|---|---|---|---|
| ReturnValue(inherited)||||||
| operationSucceeded| xsd:boolean| 処理結果です。trueの場合は、処理は成功しました。falseの場合は処理が失敗しています。| -| -| - |
| error[]| <a href="../Common/Error.md">Error</a>| エラー内容です。| -| -| - |
| biddingStrategy||||||
| biddingStrategy| <a href="BiddingStrategy.md">BiddingStrategy</a>| 自動入札設定1件あたりの実行結果です。| -| -| - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
