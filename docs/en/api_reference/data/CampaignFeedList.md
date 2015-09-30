# CampaignFeedList
CampaignFeedList object describes FeedItem information connected to Ad group.
### Service
+ [CampaignFeedService](../services/CampaignFeedService.md)

| Field | Data Type | Description | SET | 
|---|---|---|---|
| accountId| xsd:long| Account ID| Req |
| campaignId| xsd:long| Campaign ID| Req |
| placeholderType| enum <a href="./PlaceholderType_FeedItem.md">PlaceholderType</a>| FeedItem information type| Req |
| campaignFeed[]| <a href="./CampaignFeed.md">CampaignFeed</a>| A container of FeedItem information. If SET 0 case, all CampaignFeed will be deleted.| Req |
| devicePlatform| enum <a href="./DevicePlatform.md">DevicePlatform</a>| Specifies device| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
