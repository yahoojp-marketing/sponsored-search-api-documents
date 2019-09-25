

# AdGroupAdSelector

AdGroupAdSelector object describes the information and filter criteria of the Ads to be operated on.

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | Search condition: Account ID. | - | Requirement | - | - | - | |
| campaignIds[0...1000] | xsd:long | Search condition: Campaign ID.<br/>Ads returned will be from campaigns whose ids are included in this list.<br/>An empty list means there are no campaign restrictions when selecting AdGroupAds.<br/>* This field must contain distinct elements.<br/>* This field cannot contain null elements. | - | Optional | - | - | - | |
| adGroupIds[0...1000] | xsd:long | Search condition: Ad group ID.<br/>Ads returned will be from adgroups whose ids are included in this list. | - | Optional | - | - | - | |
| adIds[0...1000] | xsd:long | Search condition: Ad ID.<br/>Ads will return from ads whose ids are included in this list.<br/>If you omit adIds field, it will return all adIds under the adGroup. | - | Optional | - | - | - | |
| adTypes[0...4] | enum [AdType](./AdType.md) | Search condition: Type of ad. | - | Optional | - | - | - | |
| userStatuses[0...2] | enum [UserStatus](./UserStatus.md) | Search condition: Status of ad that been set by user.<br/>* If there is no designation, all ads in all condition will return. | - | Optional | - | - | - | |
| approvalStatuses[0...5] | enum [ApprovalStatus](./ApprovalStatus.md) | Search condition: Editorial review status. | - | Optional | - | - | - | |
| labelIds[0...1000] | xsd:long | Search condition: Label ID | - | Optional | - | - | - | |
| containsLabelId | enum [ContainsLabelId](./ContainsLabelId.md) | Search condition: Acquisition flag of label data | - | Optional | - | - | - | |
| paging | [Paging](../Common/Paging.md) | Search condition: Page of returned elements. | - | Optional | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
