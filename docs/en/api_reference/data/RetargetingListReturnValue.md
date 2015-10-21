# RetargetingListReturnValue
RetargetingListReturnValue is an object that holds results (list of all entity) of mutate method.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| ListReturnValue(inherited)|||||||
| ListReturnValue.Type| xsd:string|||||||Subtype of this ListReturnValue of instance. |
| Operation.Type| xsd:string||||||| Details of mutate process. |
| RetargetingListReturnValue|||||||
| values[]| <a href="./RetargetingListValues.md">RetargetingListValues</a>| unbounded| 0| ○| -| -| -| Result of mutate method. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

