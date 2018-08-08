# WebConversion
WebConversionオブジェクトは、ウェブページのコンバージョン測定タグやタグごとのパフォーマンスデータなどのコンバージョントラッカー情報を表します。
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ [ConversionTracker](ConversionTracker.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
 </tr>
 <tr>
  <td>snippet</td>
  <td>xsd:string</td>
  <td>トラッキングスクリプトです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>markupLanguage</td>
  <td>enum<br><a href="MarkupLanguage.md">MarkupLanguage</a></td>
  <td>マークアップ言語です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
 </tr>
 <tr>
  <td>trackingCodeType</td>
  <td>enum<br><a href="TrackingCodeType.md">TrackingCodeType</a></td>
  <td>トラッキングコードタイプです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
 </tr>
 <tr>
  <td>crossDeviceConversionFlag</td>
  <td>enum<br><a href="CrossDeviceConversionFlag.md">CrossDeviceConversionFlag</a></td>
  <td>デバイスまたぎでコンバージョンを計測するかしないかを制御するフラグです。</td>
  <td>yes</td>
  <td>Optional<br>※Default: TRUE<br>※値を指定した場合、必ず「TRUE」が設定されます。</td>
  <td>Optional<br>※値を指定した場合、必ず「TRUE」が設定されます。</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
