

# RuleBaseTargetList

RuleBaseTargetListは、ベースターゲットリストの情報を保持するオブジェクトです。

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

### Inheritance

+ [TargetingList](./TargetingList.md)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| rules[1...20] | [RuleGroup](./RuleGroup.md) | ルール設定です。 | yes | Optional<br/>`*IsAllVisitor.TRUE:Requirement` | Optional<br/>`*IsAllVisitor.TRUE:Requirement` | |
| isAllVisitor | enum [IsAllVisitorRule](./IsAllVisitorRule.md) | 全訪問者ルール設定です。 | yes | Requirement | Requirement | |
| isDateSpecific | enum [IsDateSpecificRule](./IsDateSpecificRule.md) | 期限付きルールです。<br/>※Default：FALSE | yes | Optional | - | |
| startDate | xsd:string | ルール適用開始日です。<br/>※YYYYMMDD形式です。<br/>※リクエスト日は2037/12/30まで 指定可能です。 | yes | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | |
| endDate | xsd:string | ルール適用終了日です。<br/>※YYYYMMDD形式です。<br/>※リクエスト日は2037/12/30まで 指定可能です。 | yes | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | Optional<br/>`*IsDateSpecific.TRUE:Requirement` | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
