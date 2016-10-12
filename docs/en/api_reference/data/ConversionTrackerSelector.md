# ConversionTrackerSelector
ConversionTrackerSelector object specifies ConversionTracker and operation.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Type | Description | response | get | add | set | remove| 
|---|---|---|---|---|---|---|---|
| accountId| xsd:long| Account ID.| - | Requirement | - | - | - |
| conversionTrackerIds[0..500]| xsd:long| Conversion Tracker ID. | - | Optional | - | - | - |
| statuses[0..2]| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| Conversion Status.| - | Optional | - | - | - |
| categories[0..6]| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| Conversion Category.| - | Optional | - | - | - |
| conversionTrackerTypes[0..2]| enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a>| Conversion Tracker type.| - | Optional | - | - | - |
| trackingCodeTypes[0..2]| enum <a href="./TrackingCodeType.md">TrackingCodeType</a>| Tracking type of Web conversion.| - | Optional | - | - | - |
| countingTypes[0..2]| enum <a href="./ConversionCountingType.md">ConversionCountingType</a>| Counting type of conversions.| - | Optional | - | - | - |
| excludeFromBiddings[0..2]| enum <a href="./ExcludeFromBidding.md">ExcludeFromBidding</a>| Describes whether include or exclude the data item for Auto Bidding setting.| - | Optional | - | - | - |
| dateRange| <a href="./ConversionDateRange.md">ConversionDateRange</a>| Counting period of actual conversions. If not specified, it counts conversions of entire period total.| - | Optional | - | - | - |
| paging| <a href="./Paging.md">Paging</a>| The page to be returned as response.| - | Optional | - | - | - |


<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
