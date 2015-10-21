# LogicalGroup
LogicalGroup is an object that holds combination group information.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| condition| enum <a href="./LogicalCondition.md">LogicalCondition</a>| 1| 0| ○| Opt| Opt| -| Condition of combination target list<br>* Default: OR|
| logicalOperand[]| <a href="./LogicalRuleOperand.md">LogicalRuleOperand</a>| 20| 1| ○| Req| Req| -| Target list of combination. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
