# ConversionTracker
ConversionTracker object shows ConversionTracker information such as ConversionTag and performance data by tag.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|---|
| conversionTrackerId| xsd:long| ConversionTracker ID.| Yes | - | - | Required | - |
| conversionTrackerName| xsd:string| ConversionTracker Name.| Yes | - | Required | Optional<br>Updatable | - |
| status| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| ConversionTracker Status.| Yes | - | Required | Optional<br>Updatable | - |
| category| enum<br><a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| Conversion category for tracking.<br>Please specify a purpose for conversion from ConversionTrackerCategory.<br>In the case of Call conversion, PAGE_VEIW is not specifiable.<br>In the case of App conversion, DEFAULT is only specifiable.| Yes | - | Required | Optional<br>Updatable | - |
| conversions| xsd:long| Conversions which counts as included to Auto Bidding setting.<br>countingType specifies whether one-per-click or many-per-click.| Yes | - | - | - | - |
| conversionValue| xsd:string| Conversion value to be included to auto bidding.| Yes | - | - | - | - |
| allConversions| xsd:long| Total number of conversions to be included to auto bidding and to be excluded from auto bidding.| Yes | - | - | - | - |
| allConversionVaule| xsd:string| Total value of conversions to be included to auto bidding and to be exluded from auto bidding. | Yes | - | - | - | - |
| mostRecentConversionDate| xsd:string| The most latest date when conversion occured.| Yes | - | - | - | - |
| conversionTrackerType| enum<br><a href="./ConversionTrackerType.md">ConversionTrackerType</a>| Conversion type.| Yes | - | Required | Required | - |
| userRevenueValue| xsd:string| The value of revenue of the conversion tracker specified by user. <br>When the sales revenue of 1 conversion is fixed value, you are able to review the total sales on reports by specifying the amount on this item.<br>If it is not specified on ADD request, the value "0" is set.| Yes | - | Optional | Optional<br>Updatable | - |
| countingType| enum<br><a href="./ConversionCountingType.md">ConversionCountingType</a>| Counting type for conversions.<br>*Default : MANY_PER_CLICK for web conversion, ONE_PER_CLICK for app conversion.| Yes | - | Optional<br>default：MANY_PER_CLICK | Optional | - |
| excludeFromBidding | enum<br><a href="./ExcludeFromBidding.md">ExcludeFromBidding</a>| Describes whether using the item for auto bidding setting or not.| Yes | - | Optional<br>default: FALSE (include) | Optional | - |
| measurermentPeriod | xsd:int | Counting period of conversoins (days).<br>It is available between 7 to 90 days<br>*For Mobile App Download, this period is fixed as 30 days.| Yes | - | Optional<br>default: 30 | Optional | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
