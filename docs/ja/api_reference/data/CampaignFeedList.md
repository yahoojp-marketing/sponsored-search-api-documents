# CampaignFeedList
CampaignFeedListオブジェクトは、キャンペーンに紐づけられたFeedItem情報を表します。
### Service
+ [CampaignFeedService](../services/CampaignFeedService.md)

| フィールド | データ型 | 説明 | SET | 
|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req |
| placeholderType| enum <a href="./PlaceholderType_FeedItem.md">PlaceholderType</a>| FeedItem情報の種類です。| Req |
| campaignFeed[]| <a href="./CampaignFeed.md">CampaignFeed</a>| FeedItem情報を格納するコンテナです。0件でSETするとCampaignFeedが全件削除されます。| Req |
| devicePlatform| enum <a href="./DevicePlatform.md">DevicePlatform</a>| デバイスの指定です。| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
