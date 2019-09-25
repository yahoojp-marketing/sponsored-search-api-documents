

# Ad

Ad object describes ad information.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| type | enum [AdType](./AdType.md) | Type of ad. | yes | - | Requirement | - | - | |
| advancedUrl | xsd:string | Landing Page URL. | yes | - | Requirement<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| additionalAdvancedUrls[0..9] | [AdGroupAdAdditionalAdvancedUrls](./AdGroupAdAdditionalAdvancedUrls.md) | Landing Page URL.<br/>Enter the 2nd and later of landing page URLs. | yes | - | Optional<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| advancedMobileUrl | xsd:string | Landing Page URL (Smartphone). | yes | - | Optional<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| additionalAdvancedMobileUrls[0..9] | [AdGroupAdAdditionalAdvancedMobileUrls](./AdGroupAdAdditionalAdvancedMobileUrls.md) | Landing page URL (Smartphone).<br/>Enter the 2nd and later of landing page URLs (Smartphone). | yes | - | Optional<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | - | - | |
| trackingUrl | xsd:string | Tracking URL. | yes | - | Optional | - | - | |
| customParameters | [CustomParameters](./CustomParameters.md) | Custome parameters. | yes | - | Optional | - | - | |
| url | xsd:string | Destination URL before upgrading. | yes | - | Ignore | Ignore | Ignore | |
| displayUrl | xsd:string | Display URL. | yes | - | Ignore | Ignore | Ignore | |
| headline | xsd:string | Title of ad. | yes | - | Requirement<br/>※adTypeがDYNAMIC_SEARCH_LINKED_ADの場合:Ignore。 | Ignore | Ignore | |
| description | xsd:string | Description of ad. | yes | - | Requirement | Ignore | Ignore | |
| devicePreference | enum [DevicePreference](./DevicePreference.md) | Information of Focus Device.<br/>*It enables to display your ads to smartphone devices. | yes | - | Optional<br/>※DOUBLE_TEXT_ADの場合、Ignore。 | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
