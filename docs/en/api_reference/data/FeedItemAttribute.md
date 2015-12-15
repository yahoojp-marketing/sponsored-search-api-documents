# FeedItemAttribute
FeedItemAttribute contains the value of Feed Item information.

### Service
+ [FeedItemService](../services/FeedItemService.md)

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
 </tr>
 <tr>
  <td>placeholderField</td>
  <td>enum <a href="./PlaceholderField_FeedItem.md">PlaceholderField</a></td>
  <td>Type of Feed Item.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br>* Ignore for Data Auto Insertion</td>
  <td>Requirement<br>* Ignore for Data Auto Insertion</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedAttributeId</td>
  <td>xsd:long</td>
  <td>Feed attribute ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>* Require- ment for Data Auto Insertion</td>
  <td>-<br>* Require- ment for Data Auto Insertion</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedAttributeValue</td>
  <td>xsd:string</td>
  <td>Value of Feed Item.<br>* When using for Data Auto Insertion, insert the value below for each attributes:<br>・AD_CUSTOMIZER_INTEGER<br>ex) 99999999<br>・AD_CUSTOMIZER_PRICE<br>ex) 19800 or 19,800<br>・AD_CUSTOMIZER_DATE<br>ex) 20151231 235959<br>・AD_CUSTOMIZER_STRING<br>ex) home</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reviewFeedAttributeValue</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Review staus of Feed Item.<br>*This field will show only during review.<br>* This will not show for Data Auto Insertion but it will show on feedAttributeValue field (During review or when rejected, the ad display will stop automatically).</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
