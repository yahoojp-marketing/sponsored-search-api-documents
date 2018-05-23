# MultipleFeedItemAttribute
MultipleFeedItemAttributeオブジェクトは、フィードアイテムの属性情報の値を格納します。<br>
以下のplaceholderFieldの使用時に適用するオブジェクトです。<br>
+ ADDITIONAL_ADVANCED_URLS
+ ADDITIONAL_ADVANCED_MOBILE_URLS
+ STRUCTURED_SNIPPET_VALUES

### Service
+ [FeedItemService](../../services/FeedItemService.md)

### Namespace
[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

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
  <td colspan="8"><a href="FeedItemAttribute.md">FeedItemAttribute</a>(inherited)</td>
 </tr>
 <tr>
  <td>placeholderField</td>
  <td>enum <a href="FeedItemPlaceholderField.md">FeedItemPlaceholderField</a></td>
  <td>フィードアイテム情報の種類です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>feedAttributeId</td>
  <td>xsd:long</td>
  <td>フィード属性IDです。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">MultipleFeedItemAttribute</td>
 </tr>
<tr>
<td>feedAttributeValues[]</td><td><a href="FeedAttributeValue.md">FeedAttributeValue</a></td><td>フィードアイテム情報の値です。<br>
※ADDITIONAL_ADVANCED_URLSおよびADDITIONAL_ADVANCED_MOBILE_URLS、STRUCTURED_SNIPPET_VALUESは、最大9件設定できます。
※STRUCTURED_SNIPPET_VALUESは3個以上設定する必要があります。
</td>
<td>yes</td><td>-</td><td>Requirement</td><td>Requirement<br>
<td>-</td>
</tr>
<tr>
<td>isRemove</td><td><a href="IsRemove.md">IsRemove</a></td><td>フィードアイテムを削除します。<br>
※MultipleFeedAttributeValueを削除する場合は、isRemove=TRUEを指定します。</td>
<td>-</td><td>-</td><td>-</td><td>Optional</td><td>-</td>
</tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
