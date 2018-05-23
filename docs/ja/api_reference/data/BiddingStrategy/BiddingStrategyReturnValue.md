# BiddingStrategyReturnValue
BiddingStrategyReturnValueオブジェクトは、自動入札設定を作成・更新・削除したときの結果に関する情報を表します。
### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE |
|---|---|---|---|---|---|
| ListReturnValue(inherited)||||||
| ListReturnValue.Type| xsd:string| このインスタンスの ListReturnValue のサブタイプを示します。| ー| ー| ー |
| Operation.Type| xsd:string| mutate処理の内容です。| ー| ー| ー |
| BiddingStrategyReturnValue||||||
| values[]| <a href="BiddingStrategyValues.md">BiddingStrategyValues</a>| 作成・更新・削除時の実行結果です。| ー| ー| ー |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
