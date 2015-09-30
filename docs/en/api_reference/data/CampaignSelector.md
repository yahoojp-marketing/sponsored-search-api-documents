# CampaignSelector
CampaignSelector object displays which campaigns to return.
### Service
+ [CampaignService](../services/CampaignService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID. |
| campaignIds[]| xsd:long| Campaign ID. |
| userStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| User status.|
| biddingStrategyIds[]| xsd:long| Auto bidding ID |
| paging| <a href="../data/Paging.md">Paging</a>| The starting index and number of results to return. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
