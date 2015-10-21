# RuleGroup
RuleGroupは、URL/LABELのルールをグループ化した情報を保持するオブジェクトです。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| ruleItems[]| <a href="./RuleItem.md">RuleItem</a><br> inherited <a href="./UrlRuleItem.md">UrlRuleItem</a>| 20| 1| ○| Req| Req| -| 評価条件のリストです。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
