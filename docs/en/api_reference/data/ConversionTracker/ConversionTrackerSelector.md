# ConversionTrackerSelector
ConversionTrackerSelector object specifies ConversionTracker and operation.
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
  <td>Account ID.</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>conversionTrackerIds[0..500]</td>
  <td>xsd:long</td>
  <td>Conversion Tracker ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>appIds[0..500]</td>
  <td>xsd:string</td>
  <td>App ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>statuses[0..2]</td>
  <td>enum <a href="ConversionTrackerStatus.md">ConversionTrackerStatus</a></td>
  <td>Conversion Status.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>categories[0..6]</td>
  <td>enum <a href="ConversionTrackerCategory.md">ConversionTrackerCategory</td>
  <td>Conversion Category.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>conversionTrackerTypes[0..2]</td>
  <td>enum <a href="ConversionTrackerType.md">ConversionTrackerType</a></td>
  <td>Conversion Tracker type.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>trackingCodeTypes[0..2]</td>
  <td>enum <a href="TrackingCodeType.md">TrackingCodeType</a></td>
  <td>Tracking type of Web conversion.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>countingTypes[0..2]</td>
  <td>enum <a href="ConversionCountingType.md">ConversionCountingType</a></td>
  <td>Counting type of conversions.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>excludeFromBiddings[0..2]</td>
  <td>enum <a href="ExcludeFromBidding.md">ExcludeFromBidding</a></td>
  <td>Describes whether include or exclude the data item for Auto Bidding setting.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>dateRange</td>
  <td><a href="ConversionDateRange.md">ConversionDateRange</a></td>
  <td>Counting period of actual conversions. <br>If not specified, it counts conversions of entire period total.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>The page to be returned as response. 	</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
