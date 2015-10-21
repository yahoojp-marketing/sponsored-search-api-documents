# BiddableAdGroupCriterion
BiddableAdGroupCriterion object displays biddable criterion in ad group.
### ServiceInheritance
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [BiddableAdGroupCriterion](../services/BiddableAdGroupCriterion.md)
+ [AdGroupCriterion](../services/AdGroupCriterion.md)

| Field | Data Type | Description | add | set | remove |
|---|---|---|---|---|---|
| AdGroupCriterion(inherited)||||||
| accountId| xsd:long| Account ID| Req| Req<br>NotUpdatable| Req<br>NotUpdatable |
| campaignId| xsd:long| Campaign ID| Req| Req<br>NotUpdatable| Req<br>NotUpdatable |
| campaignName| xsd:string| Campaign name| Ignore| Ignore<br>NotUpdatable| Ignore<br>NotUpdatable |
| adGroupId| xsd:long| The ad group this criterion is in.<br>This field is required and should not be null.| Req| Req<br>NotUpdatable| Req<br>NotUpdatable |
| adGroupName| xsd:string| AdGroup name| Ignore| Ignore<br>NotUpdatable| Ignore<br>NotUpdatable |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| Biddable or negative.| Req| Ignore<br>NotUpdatable| IgnoreNotUpdatable |
| criterion| <a href="./Criterion.md">Criterion</a><br>inherited <a href="./Keyword.md">Keyword</a>| The criterion part of the ad group criterion.<br>This field is required and should not be null.| Req| Req<br>Updatable| Req<br>NotUpdatable |
| BiddableAdGroupCriterion||||||
| userStatus| enum <a href="./UserStatus.md">UserStatus</a>| Current user set state of criterion.| Req| Opt<br>Updatable| IgnoreNotUpdatable |
| approvalStatus| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| Approval status.| Ignore| Ignore<br>NotUpdatable| IgnoreNotUpdatable |
| disapprovalReasonCodes| xsd:string| Reason code of reject.| Ignore| Ignore<br>NotUpdatable| Ignore<br>NotUpdatable |
| destinationUrl| xsd:string| Destination URL at keyword level (Custom URL).| Opt<br>* For Android in mobile ad download: Ignore| Opt| Ignore<br>NotUpdatable |
| biddingStrategyConfiguration| <a href="./BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a>| Auto bidding setting<br>Reference only for BudgetOptimizer.<br>Set "NONE" in biddingStrategyType to avoid Auto bidding setting.<br>This will apply upper class Auto bidding as a default.| Opt| Opt<br>Updatable| Ignore |
| biddingStrategyFailedReason| enum <a href="./BiddingStrategyFailedReason.md"> BiddingStrategyFailedReason </a>| Reason of Auto bidding failure.<br>Display only when failure occurs| Ignore| Ignore| Ignore |
| failedBiddingStrategyConfiguration| <a href="./BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a>| Failure of Auto bidding.<br>Display only when failure occurs| Ignore| Ignore| Ignore |

by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
