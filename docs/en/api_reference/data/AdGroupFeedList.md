# AdGroupFeedList
AdGroupFeedList object describes the FeedItem information connected to ad group.
### Service
+ [AdGroupFeedService](../services/AdGroupFeedService.md)

| Field | Data Type | Description | set | 
|---|---|---|---|
| accountId| xsd:long| Account ID.| Req |
| campaignId| xsd:long| Campaign ID.| Req |
| adGroupId| xsd:long| Ad Group ID.| Req |
| placeholderType| enum <a href="./AdGroupFeedPlaceholderType.md">AdGroupFeedPlaceholderType</a>| FeedItem information type.| Req |
| adGroupFeed[]| <a href="./AdGroupFeed.md">AdGroupFeed</a>| Container of FeedItem information.<br>If SET 0 case, all AdGroupFeed will be deleted.| Req |
| devicePlatform| enum <a href="./DevicePlatform.md">DevicePlatform</a>| Specifies device.<br>*If specify CALLEXTENSIONS for placeholderType, this field can be skipped.| Opt |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
