# ConversionTrackerOperation
ConversionTrackerOperation object describes ConversionTracker information and operation.
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

| Field | Data Type | Description | restriction | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum Operator| Available to use: ADD, SET| Req |
| ConversionTrackerOperation||||
| accountId| xsd:long| Account ID| Req |
| operand[]| <a href="ConversionTracker.md">ConversionTracker</a><br>inherited <a href="WebConversion.md">WebConversion</a><br>inherited <a href="AppConversion.md">AppConversion</a>| List of ConversionTracker object.<br>It includes ConversionTracker information.| Req |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
