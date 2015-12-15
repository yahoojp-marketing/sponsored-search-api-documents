# FeedItem
FeedItemオブジェクトは、フィードアイテム情報を格納します。

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedFolderId</td>
  <td>xsd:long</td>
  <td>フィードフォルダIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※データ自動 挿入の場合、Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedItemId</td>
  <td>xsd:long</td>
  <td>フィードアイテムIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>feedItemTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用フィードアイテムIDです。<br>※Sandbox環境では常に0が返ります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatus</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>審査ステータスです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes[0...n]</td>
  <td>xsd:string</td>
  <td>審査否認理由です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedItemAttribute[0...20]</td>
  <td><a href="./FeedItemAttribute.md">FeedItemAttribute</a></td>
  <td>フィードアイテムの属性情報です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>placeholderType</td>
  <td>enum <a href="./PlaceholderType_FeedItem.md">PlaceholderType</a></td>
  <td>フィードアイテムの種類です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>devicePreference</td>
  <td>enum <a href="./DevicePreference.md">DevicePreference</a></td>
  <td>優先デバイス設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※電話番号 の場合、Optional<br>※Default: SMART_PHONE</td>
  <td>Optional<br>※電話番号 の場合、Ignore</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>配信開始日です。<br>※変更の場合、空タグ指定で 設定解除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>配信終了日です。<br>※変更の場合、空タグ指定で 設定解除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>scheduling</td>
  <td><a href="./FeedItemScheduling.md">FeedItemScheduling</a></td>
  <td>配信スケジュールです。<br>※変更の場合、空タグ指定で 設定解除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingCampaign</td>
  <td><a href="./TargetingCampaign.md">TargetingCampaign</a></td>
  <td>フィードアイテムで使用する キャンペーンです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※データ自動 挿入の場合、Requirement</td>
  <td>-<br>※データ自動 挿入の場合、Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingAdGroup</td>
  <td><a href="./TargetingAdGroup.md">TargetingAdGroup</a></td>
  <td>フィードアイテムで使用する 広告グループです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※データ自動 挿入の場合、Optional</td>
  <td>-<br>※データ自動 挿入の場合、Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingKeyword</td>
  <td><a href="./TargetingKeyword.md">TargetingKeyword</a></td>
  <td>フィードアイテムで使用する キーワードです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※データ自動 挿入の場合、Optional</td>
  <td>-<br>※データ自動 挿入の場合、Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>カスタムパラメータです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※クイック リンクの場合、Optional</td>
  <td>-<br>※クイック リンクの場合、Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reviewCustomParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>配信審査中のカスタムパラメータです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advanced</td>
  <td>enum <a href="./Advanced.md">Advanced</a></td>
  <td>アドバンスドURL対応のフラグです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※クイック リンクの場合、Optional<br>※Default: TRUE</td>
  <td>-<br>※クイック リンクの場合、Optional<br>※Default: TRUE</td>
  <td>-</td>
 </tr>
</table>
<br>
 【devicePreferenceに関する注意事項】<br>
1. FeedItem情報がCALLEXTENSIONの場合は、devicePreferenceは自動的にSMART_PHONEに設定されます。<br>
2. FeedItem情報がQUICKLINKの場合は、devicePreferenceはオプションです。<br>
3. FeedItem情報がQUICKLINKの場合は、devicePreferenceの値をSMART_PHONEから解除できます。<br>
　　解除するときは、SOAPリクエストにdevicePreferenceに空の値を挿入してください。<br>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
