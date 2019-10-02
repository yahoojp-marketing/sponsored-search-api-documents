# WebConversion
WebConversionオブジェクトは、ウェブページのコンバージョン測定タグやタグごとのパフォーマンスデータなどのコンバージョントラッカー情報を表します。
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ [ConversionTracker](ConversionTracker.md)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| snippet | xsd:string | 従来のコンバージョンタグです。 | yes | Ignore | Ignore |
| advancedSnippet | xsd:string | リニューアル版のコンバージョンタグは、従来のタグよりもブラウザーなどの環境の影響を受けづらい新しいフォーマットです。<br/> 詳細は[ヘルプ](https://support-marketing.yahoo.co.jp/promotionalads/ss/articledetail?lan=ja&aid=1159)を参照 | yes | Ignore | Ignore |
| markupLanguage | enum [MarkupLanguage](./MarkupLanguage.md) | マークアップ言語です。 | yes | Requirement | Optional<br>Updatable |
| trackingCodeType | enum [TrackingCodeType](./TrackingCodeType.md) | トラッキングコードタイプです。 | yes | Requirement | Optional<br>Updatable |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
