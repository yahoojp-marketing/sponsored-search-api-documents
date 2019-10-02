# WebConversion
WebConversion describes ConversionTracker information such as ConversionTag and performance data by tag.
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ [ConversionTracker](ConversionTracker.md)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| snippet | xsd:string | Previous tag of Conversion. | yes | Ignore | Ignore |
| advancedSnippet | xsd:string | The new format of conversion tag avoids the impacts such as changes made to the browser. <br/> [Help Page](https://support-marketing.yahoo.co.jp/promotionalads/ss/articledetail?lan=en&aid=353) | yes | Ignore | Ignore |
| markupLanguage | enum [MarkupLanguage](./MarkupLanguage.md) | Tag of Conversion. | yes | Requirement | Optional<br>Updatable |
| trackingCodeType | enum [TrackingCodeType](./TrackingCodeType.md) | Tracking code type. | yes | Requirement | Optional<br>Updatable |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
