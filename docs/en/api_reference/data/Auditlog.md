# Auditlog
Auditlog object displays the log of Operation History.
### Service
+ [CustomerSyncService](../services/CustomerSyncService.md)

| Field | Data Type | Description | 
|---|---|---|
| updatedTime| xsd:string| The updated time. |
| entityType| xsd:string| The type of changed entity. |
| eventType[]| enum <a href="../data/EventType.md">EventType</a>| The operation when an entity changed. |
| sourceType| enum <a href="../data/SourceType.md">SourceType</a>| Specified a change from which systems. |
| accountId| xsd:long| It is account ID of the changed data. |
| campaigneId| xsd:long| It is campaign ID of the changed data. |
| adGroupId| xsd:long| It is ad group ID of the changed data. |
| criterionId| xsd:long| It is criterion ID of the changed data. |
| adId| xsd:long| It is ad ID of the changed data. |
| feedItemId| xsd:long| It is FeedItem information ID of the changed data. |
| biddingStrategyId| xsd:long| Auto bidding ID. |
| feedFolderId| xsd:long| Feed folder ID. |
| targetListId| xsd:long| Target list ID. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
