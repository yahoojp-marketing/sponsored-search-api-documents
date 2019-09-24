

# TargetingList

TargetingList is an object that holds retargeting information (target list).

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| accountId | xsd:long | Account ID. | yes | Requirement | Requirement | |
| owner | enum [TargetListOwner](./TargetListOwner.md) | Target list owner information. | yes | - | - | |
| retargetingAccountStatus | [RetargetingAccountStatus](./RetargetingAccountStatus.md) | Status of Retargeting account. | yes | - | - | |
| targetListId | xsd:long | Target List ID. | yes | - | Requirement | |
| targetListTrackId | xsd:long | Tracking ID of Target list. | yes | - | - | |
| targetListType | enum [TargetListType](./TargetListType.md) | Type of Target List. | yes | Requirement | Requirement | |
| targetListName | xsd:string | Target List name. | yes | Requirement | Optional | |
| targetListDescription | xsd:string | Description of Target List. | yes | Optional | Optional | |
| closingReason | enum [ClosingReason](./ClosingReason.md) | Reason for Closing. | yes | Ignore | Ignore | |
| reachStorageStatus | enum [ReachStorageStatus](./ReachStorageStatus.md) | Flag status of holding Cookie.<br/>*Default: OPEN<br/>*Always be &#34;OPEN&#34; for default list. | yes | Optional<br>`*LogicalTargetList:Ignore` | Optional<br>`*LogicalTargetList:Ignore` | |
| reachStorageSpan | xsd:long | Days to hold Cookie.<br/>*Default: 180<br/>*Can set from 1-540 days | yes | ‐ | Optional<br>`*LogicalTargetList:Ignore` | |
| reach | xsd:long | Number of users stored to the list. | yes | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
