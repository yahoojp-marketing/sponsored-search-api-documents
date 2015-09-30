# AdGroupAdSelector
Target ad and filter conditions which AdGroupAd to return.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| ID of account. |
| campaignIds[]| xsd:long| Ads returned will be from campaigns whose ids are included in this list. <br>An empty list means there are no campaign restrictions when selecting AdGroupAds.<br>This field must contain distinct elements. <br>This field cannot contain null elements. |
| adGroupIds[]| xsd:long| Ads returned will be from adgroups whose ids are included in this list. |
| adIds[]| xsd:long| Ads returned will be from ads whose ids are included in this list. <br>If you omit adIds field, return all of adIds under the adGroup,. |
| adTypes[]| enum <a href="../data/AdType.md">AdType</a>| Type of the ads. |
| userStatus[]| enum <a href="../data/UserStatus.md">UserStatus</a>| User status. |
| approvalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| Editorial review status. |
| paging| <a href="../data/Paging.md">Paging</a>| The page that is returned as a page. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
