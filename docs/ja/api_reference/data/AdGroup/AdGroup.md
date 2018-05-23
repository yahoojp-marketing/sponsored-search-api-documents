# AdGroup
AdGroup オブジェクトは、広告グループを表します。

### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>campaignTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用キャンペーンIDです。<br>※Sandbox環境では常に0が返却されます。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>広告グループIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>adGroupTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用広告グループIDです。<br>※Sandbox環境では常に0が返ります。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>広告グループ名です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>ユーザーにより設定される掲載状況です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyConfiguration</td>
  <td><a href="AdGroupBiddingStrategy.md">AdGroupBiddingStrategy</a></td>
 <td>現在有効な入札設定です。<br>※2017年11月15日以降は設定、変更できません。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
<tr>
<td>biddingStrategyFailedReason</td>
<td>enum <a href="BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a></td>
<td>自動入札の設定に失敗した理由です。<br>※失敗時のみレスポンス時に表示されます。</td>
<td>yes</td>
<td>Ignore</td>
<td>Ignore</td>
<td>Ignore</td>
</tr>
<tr>
<td>failedBiddingStrategyConfiguration</td>
<td><a href="AdGroupBiddingStrategy.md">AdGroupBiddingStrategy</a></td>
<td>登録に失敗した自動入札設定内容です。<br>※失敗時のみレスポンス時に表示されます。</td>
<td>yes</td>
<td>Ignore</td>
<td>Ignore</td>
<td>Ignore</td>
</tr>
<tr>
  <td>settings[0...1]</td>
  <td><a href="AdGroupSettings.md">AdGroupSettings</a><br>inherited <a href="TargetingSetting.md">TargetingSetting</a></td>
  <td>ターゲット設定です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>トラッキングURLです。<br>※キャンペーンがアプリキャンペーンでAndroidの場合、設定はできません。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>※こちらが審査中の場合、編集はできません。<br>※変更がない場合、審査対象とはなりません。</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>カスタムパラメータです。<br>※キャンペーンがアプリキャンペーンでAndroidの場合、設定はできません。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>※トラッキングURLが審査中の場合、編集はできません。<br>※変更がない場合、審査対象とはなりません。</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>urlReviewData</td>
  <td><a href="UrlReviewData.md">UrlReviewData</a></td>
  <td>URLの審査状況です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupAdRotationMode</td>
  <td><a href="AdGroupAdRotationMode.md">AdGroupAdRotationMode</a></td>
  <td>広告の表示の最適化設定です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
