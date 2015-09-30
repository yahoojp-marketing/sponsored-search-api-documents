# FeedItem
FeedItem is a container of FeedItem information.
### Service
+ [FeedItemService](../services/FeedItemService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| yes| Ignore| Ignore| Ignore| Account ID |
| feedFolderId| long| 1| 0| yes| Ignore(AD_CUSTOMIZER：Requirement)| Ignore| Ignore| Feed Folder ID |
| feedItemId| long| 1| 0| yes| Ignore| RequirementNot updatable| RequirementNot updatable| FeedItem ID |
| approvalStatus| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| 1| 0| yes| Ignore| Ignore| Ignore| Approval status |
| disapprovalReasonCodes| string| unbounded| 0| yes| Ignore| Ignore| Ignore| Reason for disapproval |
| feedItemAttribute| <a href="./FeedItemAttribute.md">FeedItemAttribute</a>| unbounded| 0| yes| Requirement| RequirementUpdatable| Ignore| FeedItem information |
| placeholderType| enum <a href="./PlaceholderType_FeedItem.md">PlaceholderType</a>| 1| 0| yes| Requirement| RequirementNot updatable| RequirementNot updatable| FeedItem type |
| devicePreference| enum <a href="./DevicePreference.md">DevicePreference</a>| 1| 0| yes| OptionalUpdatable| OptionalUpdatable| Ignore| Device preference |
| startDate| string| 1| 0| yes| OptionalUpdatable| OptionalUpdatable| Ignore| Start date of displaySetting will be canceled by leaving here blank on set |
| endDate| string| 1| 0| yes| OptionalUpdatable| OptionalUpdatable| Ignore| End date of displaySetting will be canceled by leaving here blank on set |
| scheduling| <a href="./FeedItemScheduling.md">FeedItemScheduling</a>| 1| 0| yes| OptionalUpdatable| OptionalUpdatable| Ignore| Schedule of displaySetting will be canceled by leaving here blank on set |
| targetingCampaign| <a href="./TargetingCampaign.md">TargetingCampaign</a>| 1| 0| yes| Ignore(AD_CUSTOMIZER：Requirement)| Ignore(AD_CUSTOMIZER：Requirement)| Ignore| Targeting campaign for Data auto insertion. |
| targetingAdGroup| <a href="./TargetingAdGroup.md">TargetingAdGroup</a>| 1| 0| yes| Ignore(AD_CUSTOMIZER：Requirement)| Ignore(AD_CUSTOMIZER：Requirement)| Ignore| Targeting ad group for Data auto insertion. |
| targetingKeyword| <a href="./TargetingKeyword.md">TargetingKeyword</a>| 1| 0| yes| Ignore(AD_CUSTOMIZER：Optional)| Ignore(AD_CUSTOMIZER：Optional)| Ignore| Targeting keyword for Data auto insertion. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
