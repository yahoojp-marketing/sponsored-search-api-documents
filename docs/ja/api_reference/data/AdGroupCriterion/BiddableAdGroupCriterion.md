# BiddableAdGroupCriterion
BiddableAdGroupCriterionオブジェクトは、広告グループの単価設定可能（包含）クライテリアです。

### Service
+ [AdGroupCriterionService](../../services/AdGroupCriterionService.md)

### Namespace
[AdGroupCriterionService#Namespace](../../services/AdGroupCriterionService.md#namespace)

### Inheritance
+ [AdGroupCriterion](AdGroupCriterion.md)

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
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>campaignTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用キャンペーンIDです。</td>
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
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>adGroupTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用広告グループIDです。</td>
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
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>criterionUse</td>
  <td>enum<br><a href="AdGroupCriterionUse.md">AdGroupCriterionUse</a></td>
  <td>クライテリアを単価設定可能にするか 除外にするかを選択します。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>criterion</td>
  <td><a href="Criterion.md">Criterion</a><br>inherited <a href="Keyword.md">Keyword</a></td>
  <td>広告グループのクライテリアです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td colspan="8">BiddableAdGroupCriterion</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum<br><a href="UserStatus.md">UserStatus</a></td>
  <td>ユーザーにより設定される広告の掲載状況です。<br>※指定しない場合は、フィルタ条件にすべての 掲載状況が含まれます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatus</td>
  <td>enum<br><a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>審査ステータスです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes</td>
  <td>xsd:string</td>
  <td>審査否認コードです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>destinationUrl</td>
  <td>xsd:string</td>
  <td>移行前のカスタムURLです。<br>※空で設定すると、既存の移行前の カスタムURLは削除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>reviewDestinationUrl</td>
  <td>xsd:string</td>
  <td>移行前の配信審査中のカスタムURLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bid</td>
  <td><a href="Bid.md">Bid</a></td>
  <td>入札価格</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td>advancedUrl</td>
  <td>xsd:string</td>
  <td>移行後のカスタムURLです。<br>※空で設定すると、既存の移行後の カスタムURLは削除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※移行してtracking Urlを指定している場合、Requirement<br>※移行しない（advanced=FALSE）場合、Ignore</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewAdvancedUrl</td>
  <td>xsd:string</td>
  <td>移行後の配信審査中のカスタムURLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>additionalAdvancedUrls</td>
  <td><a href="AdGroupCriterionAdditionalAdvancedUrls.md">AdGroupCriterionAdditionalAdvancedUrls</a></td>
  <td>最終リンク先URLの追加設定です。<br>設定にはadvancedUrlの設定が必要です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>advancedMobileUrl</td>
  <td>xsd:string</td>
  <td>カスタムURL（スマートフォン）です。<br>※空で設定すると、既存のカスタムURL （スマートフォン）は削除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※移行しない（advanced=FALSE）場合、Ignore</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewAdvancedMobileUrl</td>
  <td>xsd:string</td>
  <td>配信審査中のカスタムURL（スマートフォン）です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>additionalAdvancedMobileUrls</td>
  <td><a href="AdGroupCriterionAdditionalAdvancedMobileUrls.md">AdGroupCriterionAdditionalAdvancedMobileUrls</a></td>
  <td>スマートフォン用URLの追加設定です。<br>設定にはAdvancedMobileUrlsの設定が必要です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
 <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>トラッキングURLです。<br>※空で設定すると、既存のトラッキングURLは 削除されます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewTrackingUrl</td>
  <td>xsd:string</td>
  <td>配信審査中のトラッキングURLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <td>customParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>カスタムパラメータです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※移行しない（advanced=FALSE）場合、Ignore</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <td>reviewCustomParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>配信審査中のカスタムパラメータです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>

</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
