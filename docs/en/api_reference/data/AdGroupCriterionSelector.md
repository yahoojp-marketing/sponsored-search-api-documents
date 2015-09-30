# AdGroupCriterionSelector
AdGroupCriterionSelector object displays which ad groups criteria to return.
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd: long| Account ID |
| campaignIds[]| xsd: long| Campaign ID |
| adGroupIds[]| xsd: long| AdGroup ID |
| criterionIds[]| xsd: long| Criterion ID If you omit criterionIds field, return all of criterionIds under the adGroup. |
| criterionUse| enum <a href="../data/CriterionUse.md">CriterionUse</a>| Selects the criteria to return by the way they are used. e.g. biddable, negative. This field must contain distinct elements. This field must not contain null elements. |
| userStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| Biddable criteria's user status must be one of UserStatus. This field must contain distinct elements. This field must not contain null elements. |
| biddingStrategyIds[]| xsd:long| Auto bidding ID |
| approvalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| Editorial review status. |
| paging| <a href="../data/Paging.md">Paging</a>| The page that is returned as a page. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
