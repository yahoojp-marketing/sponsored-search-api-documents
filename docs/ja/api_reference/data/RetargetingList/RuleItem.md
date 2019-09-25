

# RuleItem

RuleItemは、ルールの評価条件を保持するオブジェクトです。

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| ruleType | enum [RuleType](./RuleType.md) | 評価条件の種別です。 | yes | Requirement | Requirement | |
| operator | enum [RuleOperator](./RuleOperator.md) | 評価式です。 | yes | Requirement | Requirement | |
| value | xsd:string | 評価値です。<br/>※括弧（()）、シングルクォート（&#39;）、ダブルクォート（&#34;）、タブ（\t）は利用できません。<br/>※250文字まで指定可能です。 | yes | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
