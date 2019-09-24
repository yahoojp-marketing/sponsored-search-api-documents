

# RetargetingListSelector

RetargetingListSelector is an object that holds search condition (parameter) of get method.

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | Search conditon: Account ID. | yes | Requirement | |
| targetListIds[0...1000] | xsd:long | Search conditon: Target List ID. | yes | Optional | |
| targetListTypes[0...3] | enum [TargetListType](./TargetListType.md) | Search conditon: Type of Target list type. | yes | Optional | |
| owner | enum [TargetListOwner](./TargetListOwner.md) | Search conditon: Target list owner information. | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | Search conditon: Page of results. | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
