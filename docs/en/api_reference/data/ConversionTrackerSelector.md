# ConversionTrackerSelector
ConversionTrackerSelector object specifies ConversionTracker and operation.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Data Type | Description | restriction | 
|---|---|---|---|
| accountId| xsd:long| Account ID| Req |
| conversionTrackerIds[]| xsd:long| ConversionTracker ID| - |
| statuses[]| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| ConversionTracker Status| - |
| categories[]| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| Conversion Category| - |
| conversionTrackerTypes[]| enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a>| Specifies ConversionTracker Type| - |
| trackingCodeTypes[]| enum <a href="./TrackingCodeType.md">TrackingCodeType</a>| Tracking　Code| - |
| dateRange| <a href="./ConversionDateRange.md">ConversionDateRange</a>| It is an aggregate period of conversion performance.If not specified, the entire period will be subject to.| - |
| paging| <a href="./Paging.md">Paging</a>| Page returned as response|  |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
