# TargetingKeyword
TargetingKeyword contains keyword setting for Data auto insertion.
### Service
+ [FeedItemService](../services/FeedItemService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| targetingKeywordId| long| 1| 0| yes| Ignore| Optional| Ignore| ID that identify the Targeting keyword (text).<br>To deactive the setting, set "0". |
| text| string| 1| 0| yes| Requirement| Requirement| Ignore| Keyword text.<br>(Maximum of 80 character and/or 10 words) |
| matchType| enum <a href="./KeywordMatchType.md">KeywordMatchType</a>| 1| 0| yes| Requirement| Requirement| Ignore| Match type.<br>Same match type as used for match type for search. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
