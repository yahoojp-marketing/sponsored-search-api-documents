# ConversionTrackerSelector
ConversionTrackerSelectorオブジェクトは、操作の対象となるコンバージョントラッカーおよび操作を指定します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Type | Description | response | get | add | set | remove| 
|---|---|---|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| - | Requirement | - | - | - |
| conversionTrackerIds[0..500]| xsd:long| コンバージョントラッカーIDです。| - | Optional | - | - | - |
| statuses[0..2]| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| コンバージョンステータスです。| - | Optional | - | - | - |
| categories[0..6]| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| コンバージョンカテゴリです。| - | Optional | - | - | - |
| conversionTrackerTypes[0..2]| enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a>| コンバージョントラッカーの種別です。| - | Optional | - | - | - |
| trackingCodeTypes[0..2]| enum <a href="./TrackingCodeType.md">TrackingCodeType</a>| Webコンバージョンのトラッキング種別です。| - | Optional | - | - | - |
| countingTypes[0..2]| enum <a href="./ConversionCountingType.md">ConversionCountingType</a>| コンバージョンの計測方法です。| - | Optional | - | - | - |
| excludeFromBiddings[0..2]| enum <a href="./ExcludeFromBidding.md">ExcludeFromBidding</a>| 自動入札設定で使用するかを表します。| - | Optional | - | - | - |
| dateRange| <a href="./ConversionDateRange.md">ConversionDateRange</a>| コンバージョン実績の集計期間です。指定がない場合は、全期間が対象となります。| - | Optional | - | - | - |
| paging| <a href="./Paging.md">Paging</a>| レスポンスとして戻されるページです。| - | Optional | - | - | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
