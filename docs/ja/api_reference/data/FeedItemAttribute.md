# FeedItemAttribute
FeedItemAttributeオブジェクトは、フィードアイテムの属性情報の値を格納します。

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
  <td>フィードアイテム情報の種類です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br>※データ自動 挿入の場合、Ignore</td>
  <td>Requirement<br>※データ自動 挿入の場合、Ignore</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedAttributeId</td>
  <td>xsd:long</td>
  <td>フィード属性IDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※データ自動 挿入の場合、Requirement</td>
  <td>-<br>※データ自動 挿入の場合、Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedAttributeValue</td>
  <td>xsd:string</td>
  <td>フィードアイテム情報の値です。<br>※データ自動挿入をご利用の 場合は、各属性については以下 のように入力 してください：<br>・AD_CUSTOMIZER_INTEGER<br>ex) 99999999<br>・AD_CUSTOMIZER_PRICE<br>ex) 19800 or 19,800<br>・AD_CUSTOMIZER_DATE<br>ex) 20151231 235959<br>・AD_CUSTOMIZER_STRING<br>ex) home</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reviewFeedAttributeValue</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>フィードアイテム情報が審査 ステータスです。<br>※審査中のときのみレスポンス 時に 表示されます。<br>※データ自動挿入のみreview FeedAttributeValueを利用されず、 feedAttributeValueで表示が そのまま置き換わります（審査中 及び掲載不可の場合は配信が 自動的に停止されます）。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
