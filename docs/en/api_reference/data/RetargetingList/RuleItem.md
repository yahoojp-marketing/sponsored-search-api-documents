

# RuleItem

RuleItem is an object that holds evaluation condition of rule.

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| ruleType | enum [RuleType](./RuleType.md) | Type of evaluation condition. | yes | Requirement | Requirement | |
| operator | enum [RuleOperator](./RuleOperator.md) | Evaluation type. | yes | Requirement | Requirement | |
| value | xsd:string | Evaluation value.<br/>*Cannot use: bracket, single quote, double quote, and tab.<br/>*Can select up to 250 characters. | yes | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
