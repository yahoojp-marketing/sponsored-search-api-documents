

# Location

Locationオブジェクトは、地域設定情報を格納します。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| targetId | xsd:string | 地域種別コードです。 | yes | Requirement | Optional | Ignore | |
| type | enum [CriterionTypeFeedItem](./CriterionTypeFeedItem.md) | クライテリオンタイプです。 | yes | Optional<br/>※default：LOCATION | Optional | Ignore | |
| geoTargetingRestriction | enum [FeedItemGeoRestriction](./FeedItemGeoRestriction.md) | 地域設定の配信を制御します。 | yes | Optional<br/>※default：NONE | Optional | Ignore | |
| isRemove | enum [IsRemove](./IsRemove.md) | 削除フラグです。 | yes | Ignore | Optional<br/>※地域設定を解除する場合は、isRemoveにTRUEを指定します。<br/>解除後は、geoTargetingRestrictionにNONEが設定されます。 | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
