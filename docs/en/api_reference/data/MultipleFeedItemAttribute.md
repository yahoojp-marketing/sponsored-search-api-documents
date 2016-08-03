# MultipleFeedItemAttribute
MultipleFeedItemAttribute object holds the value of FeedItem attribution information.<br>
This object is applied when the following placeholderFields are used.<br>
+ ADDITIONAL_ADVANCED_URLS
+ ADDITIONAL_ADVANCED_MOBILE_URLS

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
  <td colspan="8"><a href="./FeedItemAttribute.md">FeedItemAttribute</a>(inherited)</td>
 </tr>
 <tr>
  <td>placeholderField</td>
  <td>enum <a href="./FeedItemPlaceholderField.md">FeedItemPlaceholderField</a></td>
  <td>FeeItem information type.</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>feedAttributeId</td>
  <td>xsd:long</td>
  <td>Feed attribute ID.</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">MultipleFeedItemAttribute</td>
 </tr>
<tr>
<td>feedAttributeValues[]</td><td><a href="./FeedAttributeValue.md">FeedAttributeValue</a></td><td>Value of FeedItem information.<br>
*ADDITIONAL_ADVANCED_URLS and ADDITIONAL_ADVANCED_MOBILE_URLS can be set up to 9 items.
</td>
<td>yes</td><td>-</td><td>Requirement</td><td>Requirement<br>
<td>Ignore</td>
</tr>
<tr>
<td>isRemove</td><td><a href="./IsRemove.md">IsRemove</a></td><td>Remove FeedItem.<br>
*To remove MultipleFeedAttributeValue, need to specify "isRemove=TRUE".
</td>
<td>-</td><td>-</td><td>Ignore</td><td>Optional</td><td>Ignore</td>
</tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
