# FeedItemAttribute
FeedItemAttributeオブジェクトは、フィードアイテムの属性情報の値を格納します。

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
  <td>placeholderField</td>
  <td>enum <a href="FeedItemPlaceholderField.md">FeedItemPlaceholderField</a></td>
  <td>フィードアイテム情報の種類です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br>※アドカスタマイザーの場合、Ignore</td>
  <td>Requirement<br>※アドカスタマイザーの場合、Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>feedAttributeId</td>
  <td>xsd:long</td>
  <td>フィード属性IDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore<br>※アドカスタマイザーの場合、Requirement</td>
  <td>Ignore<br>※アドカスタマイザーの場合、Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
