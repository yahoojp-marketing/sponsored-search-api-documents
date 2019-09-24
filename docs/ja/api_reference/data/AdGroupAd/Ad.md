

# Ad

Adオブジェクトは、広告に関する情報を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| type | enum [AdType](./AdType.md) | 広告の種類です。 | yes | - | Requirement | - | - | |
| advancedUrl | xsd:string | 最終リンク先URLです。 | yes | - | Requirement<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| additionalAdvancedUrls[0..9] | [AdGroupAdAdditionalAdvancedUrls](./AdGroupAdAdditionalAdvancedUrls.md) | 最終リンク先URLです。<br/>2件目以降の最終リンク先URLを設定します。 | yes | - | Optional<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| advancedMobileUrl | xsd:string | 最終リンク先URL（スマート フォン）です。 | yes | - | Optional<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| additionalAdvancedMobileUrls[0..9] | [AdGroupAdAdditionalAdvancedMobileUrls](./AdGroupAdAdditionalAdvancedMobileUrls.md) | 最終リンク先URL（スマート フォン）です。<br/>2件目以降の最終リンク先URL（スマート フォン）<br/>を設定します。 | yes | - | Optional<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| trackingUrl | xsd:string | トラッキングURLです。 | yes | - | Optional | - | - | |
| customParameters | [CustomParameters](./CustomParameters.md) | カスタムパラメータです。 | yes | - | Optional | - | - | |
| url | xsd:string | 移行前のリンク先URLです。 | yes | - | Ignore | Ignore | Ignore | |
| displayUrl | xsd:string | 表示URLです。 | yes | - | Ignore | Ignore | Ignore | |
| headline | xsd:string | タイトル文です。 | yes | - | Requirement<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | Ignore | Ignore | |
| description | xsd:string | 説明文です。 | yes | - | Requirement | Ignore | Ignore | |
| devicePreference | enum [DevicePreference](./DevicePreference.md) | 優先デバイスです。<br/>※スマートフォンに優先的に配信します。 | yes | - | Optional<br/>※DOUBLE_TEXT_ADの場合、Ignore。 | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
