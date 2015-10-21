# UrlRuleItem
UrlRuleItem is an object that holds evaluation of URL rules.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
|RuleItem(inherited)|||||||
| ruleType| enum <a href="./RuleType.md">RuleType</a>| 1| 1| ○| Req| Req| -| Type of evaluation condition. |
| operator| enum <a href="./RuleOperator.md">RuleOperator</a>| 1| 1| ○| Req| Req| -| Evaluation type.|
| value| string| 1| 1| ○| Req| Req| -| Evaluation value.<br>* bracket, single quote, double quote, and tab cannot be used.<br>* Can select up to 250 characters.|
|UrlRuleItem |||||||
| urlKey| enum <a href="./UrlRuleKey.md">UrlRuleKey</a>| 1| 1| ○| Req| Req| -| Evaluation items (URL / Refer URL). |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
