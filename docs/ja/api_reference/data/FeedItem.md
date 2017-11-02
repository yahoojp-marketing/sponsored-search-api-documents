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
  <td>-<br>※アドカスタマイザーの場合、Requirement</td>
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
  <td><a href="./FeedItemAttribute.md">FeedItemAttribute</a><br>
  inherited<br>
  <a href="./SimpleFeedItemAttribute.md">SimpleFeedItemAttribute</a><br>
  <a href="./MultipleFeedItemAttribute.md">MultipleFeedItemAttribute	</a><br>
  </td>
  <td>フィードアイテムの属性情報です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>placeholderType</td>
  <td>enum <a href="./FeedItemPlaceholderType.md">FeedItemPlaceholderType</a></td>
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
  <td>優先デバイス設定です。<br>※空で設定すると、既存の優先 デバイス設定は削除されます（電話番号以外のみ）。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※電話番号オプションの場合、Optional<br>※Default: SMART_PHONE</td>
  <td>Optional<br>※電話番号オプションの場合、Ignore</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>配信開始日です。<br>※空で設定すると、既存の配信開始日は削除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>配信終了日です。<br>※空で設定すると、既存の配信終了日は削除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>scheduling</td>
  <td><a href="./FeedItemScheduling.md">FeedItemScheduling</a></td>
  <td>配信スケジュールです。<br>※空で設定すると、既存の配信スケジュールは削除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingCampaign</td>
  <td><a href="./TargetingCampaign.md">TargetingCampaign</a></td>
  <td>アドカスタマイザーで使用するキャンペーンです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※アドカスタマイザーの場合、Optional</td>
  <td>-<br>※アドカスタマイザーの場合、Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingAdGroup</td>
  <td><a href="./TargetingAdGroup.md">TargetingAdGroup</a></td>
  <td>アドカスタマイザーで使用する広告グループです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※アドカスタマイザーの場合、Optional</td>
  <td>-<br>※アドカスタマイザーの場合、Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetingKeyword</td>
  <td><a href="./TargetingKeyword.md">TargetingKeyword</a></td>
  <td>アドカスタマイザーで使用するキーワードです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※アドカスタマイザーの場合、Optional</td>
  <td>-<br>※アドカスタマイザーの場合、Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>カスタムパラメータです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※クイックリンクオプションの場合、Optional</td>
  <td>-<br>※クイックリンクオプションの場合、Optional</td>
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
  <td>geoTargeting</td>
  <td><a href="./Location.md">Location</a></td>
  <td>地域設定情報です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※アドカスタマイザーの場合、Optional</td>
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
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
