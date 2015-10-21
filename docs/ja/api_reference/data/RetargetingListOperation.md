# RetargetingListOperation
RetargetingListOperationは、組合せ対象のターゲットリストを保持するオブジェクトです。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| Operation(inherited)|||||||||
| operator| enum <a href="./Operator.md">Operator</a>||||||| 処理を表す演算子です。 |
| RetargetingListOperation|||||||
| accountId| long| 1| 1| ○| Req| Req| Req| アカウントIDです。|
| Operand[]| <a href="./TargetingList.md">TargetingList</a><br>inherited <a href="./DefaultTargetList.md">DefaultTargetList</a><br>inherited <a href="./RuleBaseTargetList.md">RuleBaseTargetList</a><br>inherited <a href="./LogicalTargetList.md">LogicalTargetList</a>| unbounded| 1| ○| Req| Req| Req| 操作対象ターゲットリストです。|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
