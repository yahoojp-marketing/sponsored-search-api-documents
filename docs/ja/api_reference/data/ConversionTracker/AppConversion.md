# AppConversion
AppConversionオブジェクトは、アプリコンバージョン測定タグやタグごとのパフォーマンスデータなどのアプリコンバージョントラッカー情報を表します。
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ [ConversionTracker](ConversionTracker.md)

| Field | Type | Description | Add | Set |
|---|---|---|---|---|
| appId| xsd:long| アプリケーションIDです。| Opt| Opt |
| appPlatform| enum <a href="AppPlatform.md">AppPlatform</a>| アプリコンバージョンのプラットフォームです。| Req| - |
| appConversionType| enum <a href="AppConversionType.md">AppConversionType</a>| アプリケーションコンバージョンタイプです。| Req| - |
| snippetId| xsd:long| コンバージョンIDです。| -| - |
| snippetLabel| xsd:string| コンバージョントラッカーラベルです。| -| - |
| appPostbackUrl| <a href="AppPostBackUrl.md">AppPostBackUrl</a>| ポストバックURLです。| Opt| Opt |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
