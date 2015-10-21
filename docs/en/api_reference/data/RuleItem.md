# RuleItem
RuleItem is an object that holds evaluation condition of rule.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| ruleType| enum <a href="./RuleType.md">RuleType</a>| 1| 1| ○| Req| Req| -| Type of evaluation condition. |
| operator| enum <a href="./RuleOperator.md">RuleOperator</a>| 1| 1| ○| Req| Req| -| Evaluation type.|
| value| string| 1| 1| ○| Req| Req| -| Evaluation value.<br>* bracket, single quote, double quote, and tab cannot be used.<br>* Can select up to 250 characters.|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
