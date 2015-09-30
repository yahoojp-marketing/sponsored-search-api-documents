# ConversionTrackerOperation
ConversionTrackerOperationオブジェクトは、操作の対象となるコンバージョントラッカー情報および操作の内容を表します。
### Service
+ [](../services/.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| 処理を表す演算子です。| Req |
| ConversionTrackerOperation||||
| AccountId| xsd:long| アカウントIDです。| Req |
| operand[]| <a href="./ConversionTracker.md">ConversionTracker</a>| ConversionTrackerオブジェクトの配列です。各配列にはコンバージョントラッカー情報が含まれます。| Req |
| operand[]| <a href="./ConversionTracker.md">ConversionTracker</a>[]<br><br>inherited <a href="./WebConversion.md">WebConversion</a><br><br>inherited <a href="./AppConversion.md">AppConversion</a>| ConversionTrackerオブジェクトの配列です。各配列にはコンバージョントラッカー情報が含まれます。<br>※1リクエストあたり20件まで登録ができるようになりました。| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
