# FeedItem
FeedItemオブジェクトは、FeedItem情報を格納します。
### Service
+ [FeedItemService](../services/FeedItemService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Ignore| Ignore| Ignore| アカウントIDです。 |
| feedFolderId| long| 1| 0| ○| Ignore（AD_CUSTOMIZERのみ：Requirement）| Ignore| Ignore| FeedフォルダIDです。 |
| feedItemId| long| 1| 0| ○| Ignore| RequirementNot updatable| RequirementNot updatable| FeedItemのIDです。 |
| approvalStatus| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| 1| 0| ○| Ignore| Ignore| Ignore| 審査状況です。 |
| disapprovalReasonCodes| string| unbounded| 0| ○| Ignore| Ignore| Ignore| 審査拒否理由です。 |
| feedItemAttribute| <a href="./FeedItemAttribute.md">FeedItemAttribute</a>| unbounded| 0| ○| Requirement| RequirementUpdatable| Ignore| FeedItem情報です。 |
| placeholderType| enum <a href="./PlaceholderType_FeedItem.md">PlaceholderType</a>| 1| 0| ○| Requirement| RequirementNot updatable| RequirementNot updatable| FeedItemの種類です。 |
| devicePreference| enum <a href="./DevicePreference.md">DevicePreference</a>| 1| 0| ○| OptionalUpdatable| OptionalUpdatable| Ignore| 優先デバイス設定です。 |
| startDate| string| 1| 0| ○| OptionalUpdatable| OptionalUpdatable| Ignore| 配信開始日です。setの場合、空タグ指定で設定解除されます。 |
| endDate| string| 1| 0| ○| OptionalUpdatable| OptionalUpdatable| Ignore| 配信終了日です。setの場合、空タグ指定で設定解除されます。 |
| scheduling| <a href="./FeedItemScheduling.md">FeedItemScheduling</a>| 1| 0| ○| OptionalUpdatable| OptionalUpdatable| Ignore| 配信スケジュールです。setの場合、空タグ指定で設定解除されます。 |
| targetingCampaign| <a href="./TargetingCampaign.md">TargetingCampaign</a>| 1| 0| ○| Ignore（AD_CUSTOMIZERのみ：Requirement）| Ignore（AD_CUSTOMIZERのみ：Requirement）| Ignore| 使用するキャンペーンです。 |
| targetingAdGroup| <a href="./TargetingAdGroup.md">TargetingAdGroup</a>| 1| 0| ○| Ignore（AD_CUSTOMIZERのみ：Requirement）| Ignore（AD_CUSTOMIZERのみ：Requirement）| Ignore| 使用する広告グループです。 |
| targetingKeyword| <a href="./TargetingKeyword.md">TargetingKeyword</a>| 1| 0| ○| Ignore（AD_CUSTOMIZERのみ：Requirement）| Ignore（AD_CUSTOMIZERのみ：Requirement）| Ignore| 使用するキーワードです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
