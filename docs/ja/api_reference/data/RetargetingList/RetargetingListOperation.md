

# RetargetingListOperation

RetargetingListOperationは、操作対象のターゲットリストを保持するオブジェクトです。

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | Requirement | Requirement | |
| owner | enum [TargetListOwner](./TargetListOwner.md) | ターゲットリストの所有状態を表します。※Default：OWNER | yes | Optional | - | |
| operand[1...200] | [TargetingList](./TargetingList.md)<br>inherited [DefaultTargetList](./DefaultTargetList.md)<br>inherited [RuleBaseTargetList](./RuleBaseTargetList.md)<br>inherited [LogicalTargetList](./LogicalTargetList.md) | 操作対象ターゲットリストです。 | yes | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
