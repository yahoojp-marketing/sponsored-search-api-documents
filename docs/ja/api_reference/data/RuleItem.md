# RuleItem
RuleItemは、ルールの評価条件を保持するオブジェクトです。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| ruleType| enum <a href="./RuleType.md">RuleType</a>| 1| 1| ○| Req| Req| -| 評価条件の種別です。 |
| operator| enum <a href="./RuleOperator.md">RuleOperator</a>| 1| 1| ○| Req| Req| -| 評価式です。|
| value| string| 1| 1| ○| Req| Req| -| 評価値です。<br>※括弧（()）、シングルクォート（'）、ダブルクォート（"）、タブ（\t）は利用できません。<br>※250文字まで指定可能です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
