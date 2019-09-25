

# TargetingList

TargetingListは、リターゲティング情報（ターゲットリスト）を保持するオブジェクトです。

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | Requirement | Requirement | |
| owner | enum [TargetListOwner](./TargetListOwner.md) | ターゲットリストの所有状態を表します。 | yes | - | - | |
| retargetingAccountStatus | [RetargetingAccountStatus](./RetargetingAccountStatus.md) | アカウントのリタゲ審査ステータスです。 | yes | - | - | |
| targetListId | xsd:long | ターゲットリストIDです。 | yes | - | Requirement | |
| targetListTrackId | xsd:long | ターゲットリストのトラッキング用IDです。 | yes | - | - | |
| targetListType | enum [TargetListType](./TargetListType.md) | ターゲットリスト種別です。 | yes | Requirement | Requirement | |
| targetListName | xsd:string | ターゲットリスト名です。 | yes | Requirement | Optional | |
| targetListDescription | xsd:string | ターゲットリストの説明です。 | yes | Optional | Optional | |
| closingReason | enum [ClosingReason](./ClosingReason.md) | ターゲットリストのクローズ理由です。 | yes | Ignore | Ignore | |
| reachStorageStatus | enum [ReachStorageStatus](./ReachStorageStatus.md) | Cookieの保持設定です。<br/>※Default：OPEN<br/>※デフォルトリストは「OPEN」のままです。 | yes | Optional<br>`*LogicalTargetList:Ignore` | Optional<br>`*LogicalTargetList:Ignore` | |
| reachStorageSpan | xsd:long | Cookieを保持する日数です。<br/>※Default：180<br/>※1-540日まで設定可能です。 | yes | ‐ | Optional<br>`*LogicalTargetList:Ignore` | |
| reach | xsd:long | リストに蓄積されているユーザー数です。 | yes | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
