# BiddableAdGroupCriterion
BiddableAdGroupCriterion object displays biddable criterion in ad group.
### ServiceInheritance
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [BiddableAdGroupCriterion](../services/BiddableAdGroupCriterion.md)
+ [AdGroupCriterion](../services/AdGroupCriterion.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| AdGroupCriterion(inherited)||||||
| accountId| xsd:long| Account ID| Req| ReqNotUpdatable| ReqNotUpdatable |
| campaignId| xsd:long| Campaign ID| Req| ReqNotUpdatable| ReqNotUpdatable |
| campaignName| xsd:string| Campaign name| Ignore| IgnoreNotUpdatable| IgnoreNotUpdatable |
| adGroupId| xsd:long| The ad group this criterion is in. This field is required and should not be null.| Req| ReqNotUpdatable| ReqNotUpdatable |
| adGroupName| xsd:string| AdGroup name| Ignore| IgnoreNotUpdatable| IgnoreNotUpdatable |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| Biddable or negative.| Req| IgnoreNotUpdatable| IgnoreNotUpdatable |
| criterion| <a href="./Criterion.md">Criterion</a><br>inherited <a href="./Keyword.md">Keyword</a>| The criterion part of the ad group criterion. This field is required and should not be null.| Req| ReqUpdatable| ReqNotUpdatable |
| BiddableAdGroupCriterion||||||
| userStatus| enum <a href="./UserStatus.md">UserStatus</a>| Current user set state of criterion.| Req| OptUpdatable| IgnoreNotUpdatable |
| approvalStatus| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| Approval status.| Ignore| IgnoreNotUpdatable| IgnoreNotUpdatable |
| disapprovalReasonCodes| xsd:string| <span>Reason code of reject.</span>| Ignore| IgnoreNotUpdatable| IgnoreNotUpdatable |
| destinationUrl| xsd:string| Destination URL at keyword level (Custom URL).| Optnull| Opt| IgnoreNotUpdatable |
| biddingStrategyConfiguration| <a href="./BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a>| Auto bidding setting<br>Reference only for BudgetOptimizer.<br>Set "NONE" in biddingStrategyType to avoid Auto bidding setting.<br>This will apply upper class Auto bidding as a default.| Opt| Opt(updatable)| - |
| biddingStrategyFailedReason| enum <a href="./BiddingStrategyFailedReason.md"> BiddingStrategyFailedReason </a>| Reason of Auto bidding failure<br>Display only when failure occurs| -| -| - |
| failedBiddingStrategyConfiguration| <a href="./BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a>| Failure of Auto bidding<br>Display only when failure occurs| -| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
