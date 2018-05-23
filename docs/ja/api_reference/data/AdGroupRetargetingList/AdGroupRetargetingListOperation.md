# AdGroupRetargetingListOperation
AdGroupRetargetingListOperationは、mutateメソッドで操作対象の広告グループレベルでのターゲットリスト設定を保持するオブジェクトです。

### Service
+ [AdGroupRetargetingListService](../../services/AdGroupRetargetingListService.md)

### Namespace
[AdGroupRetargetingListService#Namespace](../../services/AdGroupRetargetingListService.md#namespace)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 |
|---|---|---|---|---|---|---|---|---|
| Operation(inherited)|||||||||
| operator| enum Operator||||||| ADD、SET、REMOVEが指定可能です。 |
| AdGroupRetargetingListOperation|||||||
| accountId| long| 1| 1| -| Req| Req| Req| アカウントIDです。|
| Operand[]| <a href="AdGroupRetargetingList.md">AdGroupRetargetingList</a>| unbounded| 1| -| Req| Req| Req| 操作対象広告グループユーザのリストです。|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
