# AdGroupBidLandscape
Expected results of AdGroup.
### Service
+ [BidLandscapeService](../../services/BidLandscapeService.md)

| Field | Data Type | Description | 
|---|---|---|
| BidLandscape (inherited)|||
| campaignId| xsd:long| Campaign ID |
| adGroupId| xsd:long| Ad Group ID |
| startDate| xsd:string| The Start date |
| endDate| xsd:string| The End date |
| landscapePoints[]| <a href="LandscapePoints.md">LandscapePoints</a>| The list of Landscape Points |
| BidLandscape.Type| xsd:string| This field indicates a Landscape Subtype |
| AdGroupBidLandscape|||
| type| xsd:string<br><a href="AdGroupBidLandscapeType.md">AdGroupBidLandscapeType</a>| Type of AdGroupLandscape |
| landscapeCurrent| xsd:boolean| It selects the value of "LandscapeCurrent" |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
