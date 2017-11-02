# Location
Location object contains the information of Geographic Location.

### Service
+ [FeedItemService](../services/FeedItemService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>targetId</td>
  <td>xsd:string</td>
  <td>Location Type Code</td>
  <td>yes</td>
  <td>Required</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>type</td>
  <td>enum<br><a href="./CriterionTypeFeedItem.md">CriterionTypeFeedItem</a></td>
  <td>Criterion Type</td>
  <td>yes</td>
  <td>Optional<br>&lowast;default：LOCATION</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>geoTargetingRestriction</td>
  <td>enum<br><a href="./FeedItemGeoRestriction.md">FeedItemGeoRestriction</a></td>
  <td>Controling the ad delivery of location restriction</td>
  <td>yes</td>
  <td>Optional<br>&lowast;default：NONE</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>

 <tr>
  <td>isRemove</td>
  <td>enum<br><a href="./IsRemove.md">IsRemove</a></td>
  <td>Delete flag</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>&lowast;To remove the Geographic Location setting, specify "isRemove=TRUE".<br>After removing, geoTargetingRestriction is set to "NONE".</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
