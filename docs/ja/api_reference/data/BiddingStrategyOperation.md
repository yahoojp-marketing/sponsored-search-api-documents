# BiddingStrategyOperation
BiddingStrategyOperationオブジェクトは、自動入札設定の操作対象キャンペーンに関する情報を表します。
### Service
+ [BiddingStrategyService](../services/BiddingStrategyService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Operation(inherited)||||||
| operator| enum <a href="../data/Operator.md">Operator</a>| 処理を表す演算子です。| Req| Req| Req |
| BiddingStrategyOperation||||||
| accountId| xsd:long| アカウントIDです。| Req| Req<br>                        (notupdatable)| Req<br>                        (notupdatable) |
| operand[]| <a href="../data/BiddingStrategy_BiddingStrategy.md">BiddingStrategy</a>| 操作対象自動入札設定リストです。| Req| Req| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
