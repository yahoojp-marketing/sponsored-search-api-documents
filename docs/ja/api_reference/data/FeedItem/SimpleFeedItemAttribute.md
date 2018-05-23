# SimpleFeedItemAttribute
SimpleFeedItemAttributeオブジェクトは、フィードアイテムの属性情報の値を格納します。<br>
以下のplaceholderFieldの使用時に適用するオブジェクトです。<br>
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
<td>feedAttributeValue</td><td>xsd:string</td><td>フィードアイテム情報の値です。<br><br>
※データ自動挿入の利用時は、属性は以下のように入力してください：<br>
・AD_CUSTOMIZER_INTEGER<br>
ex) 99999999<br>
・AD_CUSTOMIZER_PRICE<br>
ex) 19800 or 19,800<br>
・AD_CUSTOMIZER_DATE<br>
ex) 20151231 235959<br>
・AD_CUSTOMIZER_STRING<br>
ex) hoge
・STRUCTURED_SNIPPET_HEADER<br>
ex) ブランド<br>
</td>
<td>yes</td><td>-</td><td>Requirement</td><td>Optional</td><td>Ignore</td>
</tr>
<tr><td>reviewFeedAttributeValue</td><td>xsd:string</td><td>審査中のフィードアイテム情報です。<br>※審査中の間のみ、レスポンス時に表示されます。</td><td>yes</td><td>-</td><td>Ignore</td><td>Ignore</td><td>Ignore</td>
</tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
