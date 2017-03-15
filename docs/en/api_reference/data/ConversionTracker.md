# ConversionTracker
ConversionTracker object shows ConversionTracker information such as ConversionTag and performance data by tag.
### Service
+ [ConversionTrackerService](../services/ConversionTrackerService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 <tr>
  <td>conversionTrackerId</td>
  <td>xsd:long</td>
  <td>ConversionTracker ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>conversionTrackerName</td>
  <td>xsd:string</td>
  <td>ConversionTracker Name.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>status</td>
  <td>enum <a href="./ConversionTrackerStatus.md">ConversionTrackerStatus</a></td>
  <td>ConversionTracker Status.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>category</td>
  <td>enum<br><a href="./ConversionTrackerCategory.md">ConversionTrackerCategory</a></td>
  <td>Conversion category for tracking.<br>Please specify a purpose for conversion from ConversionTrackerCategory.<br>In the case of Call conversion, PAGE_VEIW is not specifiable.<br>In the case of App conversion, DEFAULT is only specifiable.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>conversions</td>
  <td>xsd:long</td>
  <td>Conversions which counts as included to Auto Bidding setting.<br>countingType specifies whether one-per-click or many-per-click.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>conversionValue</td>
  <td>xsd:string</td>
  <td>Conversion value to be included to auto bidding.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>allConversions</td>
  <td>xsd:long</td>
  <td>Total number of conversions to be included to auto bidding and to be excluded from auto bidding.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>allConversionVaule</td>
  <td>xsd:string</td>
  <td>Total value of conversions to be included to auto bidding and to be exluded from auto bidding.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mostRecentConversionDate</td>
  <td>xsd:string</td>
  <td>The most latest date when conversion occured.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>conversionTrackerType</td>
  <td>enum<br><a href="./ConversionTrackerType.md">ConversionTrackerType</a></td>
  <td>Conversion type.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>userRevenueValue</td>
  <td>xsd:string</td>
  <td>The value of revenue of the conversion tracker specified by user. <br>When the sales revenue of 1 conversion is fixed value, you are able to review the total sales on reports by specifying the amount on this item.<br>If it is not specified on ADD request, the value "0" is set.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>countingType</td>
  <td>enum<br><a href="./ConversionCountingType.md">ConversionCountingType</td>
  <td>Counting type for conversions.<br>*Default : MANY_PER_CLICK for web conversion, ONE_PER_CLICK for app conversion.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>default：MANY_PER_CLICK</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>excludeFromBidding</td>
  <td>enum<br><a href="./ExcludeFromBidding.md">ExcludeFromBidding</a></td>
  <td>Describes whether using the item for auto bidding setting or not.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>default: FALSE（include）</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>measurermentPeriod</td>
  <td>xsd:int</td>
  <td>Counting period of conversoins (days).<br>It is available between 7 to 90 days<br>*For Mobile App Download, this period is fixed as 30 days.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>default: 30</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
