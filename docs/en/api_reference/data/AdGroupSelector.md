# AdGroupSelector
AdGroupSelector object displays which ad groups to return.
### Service
+ [AdGroupService](../services/AdGroupService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID. |
| campaignIds[]| xsd:long| The list of possible campaigns to be selected. <br>An empty list indicates all account campaigns as possibly being selected. <br>This field must contain distinct elements. <br>This field cannot contain null elements. |
| adGroupIds[]| xsd:long| List of ad group IDs to select. <br>If you omit ad group IDs field, return all of ad group IDs under the campaign ID. |
| userStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| User status. |
| biddingStrategyIds[]| xsd:long| Auto bidding ID. |
| paging| <a href="../data/Paging.md">Paging</a>| The page that is returned as a page. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
