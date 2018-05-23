# AppConversion
AppConversion object describes the App ConversionTracker information such as App ConversionTag and performance data by tag.
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ [ConversionTracker](ConversionTracker.md)

| Field | Data Type | Description | ADD | SET | 
|---|---|---|---|---|
| appId| xsd:long| Application ID| Opt | Opt |
| appPlatform| enum <a href="AppPlatform.md">AppPlatform</a>| AppConversion platform| Req| - |
| appConversionType| enum <a href="AppConversionType.md">AppConversionType</a>| AppConversion type| Req| - |
| snippetId| xsd:long| Converison ID| -| - |
| snippetLabel| xsd:string | Converison tracker label | -| - |
| appPostbackUrl| <a href="AppPostbackUrl.md">AppPostbackUrl</a>| Postback URL| Opt| Opt |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
