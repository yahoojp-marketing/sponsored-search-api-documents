# AppConversion
AppConversion object describes the App ConversionTracker information such as App ConversionTag and performance data by tag.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Data Type | Description | ADD | SET | 
|---|---|---|---|---|
| ConversionTracker(inherited)|||||
| accountId| xsd:long| Account ID| Req| Req |
| conversionTrackerId| xsd:long| ConversionTrackerID| -| Req |
| conversionTrackerName| xsd:string| Name of ConversionTracker| Req| Opt |
| status| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| Status of ConversionTracker| Req| Opt |
| category| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| Conversion category for tracking.<br>Please specify a purpose for conversion from ConversionTrackerCategory.<br>* In the case of Call conversion, PAGE_VIEW is not specifiable.<br>* In the case of App conversion, DEFAULT is only specifiable.| Req| Opt |
| numConversionEvents| xsd:int| Total conversions.<br>Total conversions are the count for all conversions that resulted within 30 days of 1 click of an ad.| -| - |
| conversionValue| xsd:long| Total sales by conversion.| -| - |
| mostRecentConversionDate| xsd:string| Most recent date of Conversion| -| - |
| numConvertedClicks| xsd:int| The number of Unique Conversions.<br>The unique conversion refers to the first conversion that resulted within 30 days of 1 click of an ad.<br>Even if several conversions resulted from a click of an ad, the second and further conversions are not counted.| -| - |
| conversionTrackerType| enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a>| ConversionTracker Type| Req| Req |
| userRevenueValue| xsd:string| Revenue value for ConversionTracker.<br>If fixed value is set for a conversion by user, total revenue is appeared in the report.<br>App conversion value is not assignable, download sales will be calculated as conversion value.| Req(WebConversion)<br>-(AppConversion)| Opt(WebConversion)<br>-(AppConversion) |
| AppConversion|||||
| appId| xsd:long| Application ID| Req| Opt |
| appPlatform| enum <a href="./AppPlatform.md">AppPlatform</a>| AppConversion platform| Req| Opt |
| appConversionType| enum <a href="./AppConversionType.md">AppConversionType</a>| AppConversion type| Req| Opt |
| snippetId| xsd:long| Converison ID| -| - |
| snippetLabel| xsd:string | Converison tracker label | -| - |
| appPostbackUrl| <a href="./AppPostbackUrl.md">AppPostbackUrl</a>| Postback URL| Opt| Opt |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
