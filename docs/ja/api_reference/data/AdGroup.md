# AdGroup
AdGroup オブジェクトは、広告グループを表します。

### Service
+ [AdGroupService](../services/AdGroupService.md)

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
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>campaignTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用キャンペーンIDです。<br>※Sandbox環境では常に0が返ります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>広告グループIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>adGroupTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用広告グループIDです。<br>※Sandbox環境では常に0が返ります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>広告グループ名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>ユーザーにより設定される掲載状況です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>biddingStrategyConfiguration</td>
  <td><a href="./BiddingStrategy_AdGroup.md">BiddingStrategy</a></td>
  <td>入札設定です。<br>※現在有効な入札設定がレスポンス されます。<br>※BudgetOptimizerの登録、更新は 行えません。（照会のみ可能）<br>※広告グループ単位で入札設定を 行わない場合は、biddingStrategyTypeに「NONE」を登録します。<br>※入札設定を行わない場合は、デフォルトで親エンティティの入札設定が適用されます。<br>※アプリキャンペーンでiOS を指定した場合、TARGET_CPA/ TARGET_ROASは設定できません。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>biddingStrategyFailedReason</td>
  <td>enum <a href="./BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a></td>
  <td>自動入札の設定に失敗した理由です。<br>※失敗時のみレスポンス時に表示 されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>failedBiddingStrategyConfiguration</td>
  <td><a href="./BiddingStrategy_AdGroup.md">BiddingStrategy</a></td>
  <td>登録に失敗した自動入札設定内容です。<br>※失敗時のみレスポンス時に表示 されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>settings[0...1]</td>
  <td><a href="./Settings_AdGroup.md">Settings</a><br>inherited <a href="./TargetingSetting.md">TargetingSetting</a></td>
  <td>ターゲット設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>トラッキングURLです。<br>※キャンペーンがアプリキャンペーンで Androidの場合、設定はできません。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>※こちらが審査中 の場合、編集は できません。<br>※変更がない場合、審査対象とはなりません。</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>カスタムパラメータです。<br>※キャンペーンがアプリキャンペーンで Androidの場合、設定はできません。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>※トラッキング URLが審査中の場合、編集はできません。<br>※変更がない場合、審査対象とはなりません。</td>
  <td>-</td>
 </tr>
 <tr>
  <td>urlReviewData</td>
  <td><a href="./UrlReviewData.md">UrlReviewData</a></td>
  <td>URLの審査状況です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
