# ConversionTracker
ConversionTrackerオブジェクトは、コンバージョン測定タグやタグごとのパフォーマンスデータなどのコンバージョントラッカー情報を表します。
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|---|
| conversionTrackerId| xsd:long| コンバージョントラッカーのIDです。| Yes | - | - | Requirement | - |
| conversionTrackerName| xsd:string| コンバージョントラッカーの名称です。| Yes | - | Requirement | Optional<br>Updatable | - |
| status| enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a>| コンバージョントラッカーのステータスです。| Yes | - | Requirement | Optional<br>Updatable | - |
| category| enum<br><a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a>| トラッキング対象のコンバージョンのカテゴリです。<br>コンバージョン測定を行う目的をConversionTrackerCategoryより選んでください。<br>※電話コンバージョンの場合は、PAGE_VEIWの指定はできません。<br>※アプリコンバージョンの場合は、DEFAULTのみ指定可能です。| Yes | - | Requirement | Optional<br>Updatable | - |
| conversions| xsd:long| 自動入札設定対象のコンバージョン数です。<br>ユニークコンバージョンか総コンバージョンかは、countingTypeに依存します。| Yes | - | - | - | - |
| conversionValue| xsd:long| 自動入札設定対象のコンバージョン値です。| Yes | - | - | - | - |
| allConversions| xsd:long| 自動入札設定対象のコンバージョン数と、対象外のコンバージョン数の合計です。| Yes | - | - | - | - |
| allConversionVaule| xsd:long| 自動入札設定対象のコンバージョン値と、対象外のコンバージョン値の合計です。| Yes | - | - | - | - |
| mostRecentConversionDate| xsd:string| 直近のコンバージョン発生日です。| Yes | - | - | - | - |
| conversionTrackerType| enum<br><a href="./ConversionTrackerType.md">ConversionTrackerType</a>| コンバージョンタイプです。| Yes | - | Requirement | Requirement | - |
| userRevenueValue| xsd:string| このコンバージョントラッカーに対するユーザー指定の収益値です。<br>1コンバージョンあたりの売上金額が固定値の場合、その金額を設定することで、売上金額をレポートなどで確認できます。<br>ADDリクエスト時に未指定の場合、0が設定されます。| Yes | - | Optional | Optional<br>Updatable | - |
| countingType| enum<br><a href="./ConversionCountingType.md">ConversionCountingType</a>| コンバージョンの計測方法です。| Yes | - | Optional<br>default：MANY_PER_CLICK | Optional | - |
| excludeFromBidding | enum<br><a href="./ExcludeFromBidding.md">ExcludeFromBidding</a>| 自動入札設定で使用するかを表します。| Yes | - | Optional<br>default: FALSE（使用する） | Optional | - |
| measurermentPeriod | xsd:int | コンバージョン計測期間です（単位：日)。<br>7～90日間で設定可能です。<br>※アプリダウンロードの場合は30日間固定。| Yes | - | Optional<br>default: 30 | Optional | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
