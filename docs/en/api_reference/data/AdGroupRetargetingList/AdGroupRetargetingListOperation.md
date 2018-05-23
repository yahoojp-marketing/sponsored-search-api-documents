# AdGroupRetargetingListOperation
AdGroupRetargetingListOperation is an object that holds target ad group retargeting in mutate methods.

### Service
+ [AdGroupRetargetingListService](../../services/AdGroupRetargetingListService.md)

### Namespace
[AdGroupRetargetingListService#Namespace](../../services/AdGroupRetargetingListService.md#namespace)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description |
|---|---|---|---|---|---|---|---|---|
| Operation(inherited)|||||||||
| operator| enum Operator|||||||Available to use: ADD, SET, REMOVE |
| AdGroupRetargetingListOperation|||||||
| accountId| long| 1| 1| -| Req| Req| Req| Account ID.|
| Operand[]| <a href="AdGroupRetargetingList.md">AdGroupRetargetingList</a>| unbounded| 1| -| Req| Req| Req| List of operating ad group user.|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
