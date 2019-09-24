

# LogicalGroup

LogicalGroupは、組合せグループの情報を保持するオブジェクトです。

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| condition | enum [LogicalCondition](./LogicalCondition.md) | 組み合わせるターゲットリストの連結条件です。<br/>※Default：OR | yes | Optional | Optional | |
| logicalOperand[1...20] | [LogicalRuleOperand](./LogicalRuleOperand.md) | ターゲットタイプです。 | yes | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
