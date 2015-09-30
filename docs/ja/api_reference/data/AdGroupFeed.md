# AdGroupFeed
AdGroupFeedオブジェクトは、広告グループに紐づけられたFeedItem情報を表します。
### Service
+ [AdGroupFeedService](../services/AdGroupFeedService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| —| —| — |
| campaignId| xsd:long| キャンペーンIDです。| —| —| — |
| adGroupId| xsd:long| 広告グループIDです。| —| —| — |
| feedItemId| xsd:long| FeedItem情報のIDです。| Req| Req| Req |
| placeholderType| enum <a href="./PlaceholderType_FeedItem.md">PlaceholderType</a>| FeedItem情報の種類です。| —| —| — |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
