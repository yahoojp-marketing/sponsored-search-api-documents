# CampaignFeedSelector
CampaignFeedSelectorオブジェクトは、FeedItem情報を指定します。
### Service
+ [CampaignFeedService](../../services/CampaignFeedService.md)

### Namespace
[CampaignFeedService#Namespace](../../services/CampaignFeedService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignIds[]| xsd:long| キャンペーンIDです。 |
| feedItemIds[]| xsd:long| FeedItem情報のIDです。 |
| placeholderTypes[]| enum <a href="CampaignFeedPlaceholderType.md">CampaignFeedPlaceholderType</a>| feedItem情報の種類です。 |
| paging| <a href="../Common/Paging.md">Paging</a>| ページの取得範囲です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
