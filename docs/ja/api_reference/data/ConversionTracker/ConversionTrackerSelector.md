# ConversionTrackerSelector
ConversionTrackerSelectorオブジェクトは、操作の対象となるコンバージョントラッカーおよび操作を指定します。
### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>get</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>conversionTrackerIds[0..500]</td>
  <td>xsd:long</td>
  <td>コンバージョントラッカーIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>appIds[0..500]</td>
  <td>xsd:string</td>
  <td>アプリケーションIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>statuses[0..2]</td>
  <td>enum <a href="ConversionTrackerStatus.md">ConversionTrackerStatus</a></td>
  <td>コンバージョンステータスです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>categories[0..6]</td>
  <td>enum <a href="ConversionTrackerCategory.md">ConversionTrackerCategory</td>
  <td>コンバージョンカテゴリーです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>conversionTrackerTypes[0..2]</td>
  <td>enum <a href="ConversionTrackerType.md">ConversionTrackerType</a></td>
  <td>コンバージョントラッカーの種別です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>trackingCodeTypes[0..2]</td>
  <td>enum <a href="TrackingCodeType.md">TrackingCodeType</a></td>
  <td>ウェブコンバージョンのトラッキング種別です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>countingTypes[0..2]</td>
  <td>enum <a href="ConversionCountingType.md">ConversionCountingType</a></td>
  <td>コンバージョンの計測方法です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>excludeFromBiddings[0..2]</td>
  <td>enum <a href="ExcludeFromBidding.md">ExcludeFromBidding</a></td>
  <td>自動入札設定で使用するかを表します。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>crossDeviceConversionFlags[0..2]</td>
  <td>enum <a href="CrossDeviceConversionFlag.md">CrossDeviceConversionFlag</a></td>
  <td>デバイスまたぎでコンバージョンを計測するか、しないかを制御するフラグです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="ConversionDateRange.md">ConversionDateRange</a></td>
  <td>コンバージョン実績の集計期間です。<br>指定がない場合は、全期間が対象となります。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>データの取得範囲です。</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
