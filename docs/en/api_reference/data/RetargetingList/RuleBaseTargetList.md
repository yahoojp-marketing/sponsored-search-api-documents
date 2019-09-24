

# RuleBaseTargetList

RuleBaseTargetList is an object that holds Rule based target list information.

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

### Inheritance

+ [TargetingList](./TargetingList.md)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| rules[1...20] | [RuleGroup](./RuleGroup.md) | Setting of rules. | yes | Optional<br/>`*IsAllVisitor.TRUE:Requirement` | Optional<br/>`*IsAllVisitor.TRUE:Requirement` | |
| isAllVisitor | enum [IsAllVisitorRule](./IsAllVisitorRule.md) | Setting of all visitor rules. | yes | Requirement | Requirement | |
| isDateSpecific | enum [IsDateSpecificRule](./IsDateSpecificRule.md) | Rule with specific deadline date.<br/>*Default: FALSE | yes | Optional | - | |
| startDate | xsd:string | Start date of rule setting.<br/>*In YYYYMMDD format<br/>*Request date can be set up to 2037/12/30 | yes | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | |
| endDate | xsd:string | End date of rule setting.<br/>*In YYYYMMDD format<br/>*Request date can be set up to 2037/12/30 | yes | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
