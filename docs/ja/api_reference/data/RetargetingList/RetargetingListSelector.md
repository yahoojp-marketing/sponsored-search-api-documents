

# RetargetingListSelector

RetargetingListSelectorは、ターゲットリストのgetメソッド検索条件（実行パラメータ）を保持するオブジェクトです。

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | 検索条件：アカウントIDです。 | yes | Requirement | |
| targetListIds[0...1000] | xsd:long | 検索条件：ターゲットリストIDです。 | yes | Optional | |
| targetListTypes[0...3] | enum [TargetListType](./TargetListType.md) | 検索条件：ターゲットリストの種類です。 | yes | Optional | |
| owner | enum [TargetListOwner](./TargetListOwner.md) | 検索条件：ターゲットリストの所有状態です。 | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | 検索条件：取得範囲です。 | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
