# LogicalGroup
LogicalGroupは、組合せグループの情報を保持するオブジェクトです。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| condition| enum <a href="./LogicalCondition.md">LogicalCondition</a>| 1| 0| ○| Opt| Opt| -| 組み合わせるターゲットリストの連結条件です。<br>※Default値：OR|
| logicalOperand[]| <a href="./LogicalRuleOperand.md">LogicalRuleOperand</a>| 20| 1| ○| Req| Req| -| ターゲットタイプです。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
