# ConversionTrackerOperation
ConversionTrackerOperation object describes ConversionTracker information and operation.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

| Field | Data Type | Description | restriction | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| Operator that serves processes| Req |
| ConversionTrackerOperation||||
| accountId| xsd:long| Account ID| Req |
| operand[]| <a href="./ConversionTracker.md">ConversionTracker</a><br><br><br>			inherited <a href="./WebConversion.md">WebConversion</a><br><br><br>			inherited <a href="./AppConversion.md">AppConversion</a><br>| List of ConversionTracker object. It includes ConversionTracker information.<br><br>			* Maximum amounts per request have changed to 20.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
