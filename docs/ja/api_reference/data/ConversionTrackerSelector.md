# ConversionTrackerSelector
ConversionTrackerSelectorオブジェクトは、操作の対象となるコンバージョントラッカーおよび操作を指定します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req |
| conversionTrackerIds[]| xsd:long| コンバージョントラッカーIDです。| - |
| statuses[]| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| コンバージョンステータスです。| - |
| categories[]| enum <a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| コンバージョンカテゴリです。| - |
| conversionTrackerTypes[]| enum <a href="./ConversionTrackerType.md">ConversionTrackerType</a>| コンバージョントラッカーのタイプの指定です。| - |
| trackingCodeTypes[]| enum <a href="./TrackingCodeType.md">TrackingCodeType</a>| トラッキングコードです。| - |
| dateRange| <a href="./ConversionDateRange.md">ConversionDateRange</a>| コンバージョン実績の集計期間です。指定がない場合は、全期間が対象となります。| - |
| paging| <a href="./Paging.md">Paging</a>| レスポンスとして戻されるページです。| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
