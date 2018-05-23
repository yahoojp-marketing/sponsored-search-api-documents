# SimpleFeedItemAttribute
SimpleFeedItemAttribute object stores the value of attribution information of feed items.<br>
This object is applied for the following placeholderFields.<br>
+ LINK_TEXT
+ LINK_URL
+ ADVANCED_URL
+ ADVANCED_MOBILE_URL
+ TRACKING_URL
+ CALL_PHONE_NUMBER
+ AD_CUSTOMIZER_INTEGER
+ AD_CUSTOMIZER_PRICE
+ AD_CUSTOMIZER_DATE
+ AD_CUSTOMIZER_STRING
+ CALLOUT_TEXT
+ STRUCTURED_SNIPPET_HEADER

### Service
+ [FeedItemService](../../services/FeedItemService.md)

### Namespace
[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

### Inheritance
+ [FeedItemAttribute](FeedItemAttribute.md)

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
<td>feedAttributeValue</td><td>xsd:string</td><td>Value of feed iteim information.<br><br>
*When using data insertion, you need to enter attribution as follows:<br>
・AD_CUSTOMIZER_INTEGER<br>
ex) 99999999<br>
・AD_CUSTOMIZER_PRICE<br>
ex) 19800 or 19,800<br>
・AD_CUSTOMIZER_DATE<br>
ex) 20151231 235959<br>
・AD_CUSTOMIZER_STRING<br>
ex) home<br>
・STRUCTURED_SNIPPET_HEADER<br>
ex) brand<br>
</td>
<td>yes</td><td>-</td><td>Requirement</td><td>Optional</td><td>Ignore</td>
</tr>
<tr><td>reviewFeedAttributeValue</td><td>xsd:string</td><td>The feed item information on editorial review.<br>*It is displayed for response only on Editorial Review.</td><td>yes</td><td>-</td><td>Ignore</td><td>Ignore</td><td>Ignore</td>
</tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
