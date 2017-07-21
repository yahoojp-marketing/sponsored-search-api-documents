# リリースノート
スポンサードサーチAPI Ver.6.3<br>

## リリースバージョン
6.3 (WSDLバージョン: 6.3.0)

## バージョンアップの種類
マイナーバージョンアップ  

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

#### 1. サイトリターゲティング機能の改善
 * 代理店様配下の同一広告主様、および直接お取り引きの広告主様配下の、複数のアカウント間で共通のターゲットリストが利用可能になりました。これに伴いスポンサードサーチAPIにおいて、アカウント間で共通のターゲットリストの登録、変更などに対応しました。
 *  キャンペーンにターゲットリストを設定する際に従来の「除外」に加えて「配信」での関連付け設定が可能になりました。<br><br>

##### 対象ウェブサービス  
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)
 * [CampaignRetargetingListService](/docs/ja/api_reference/services/CampaignRetargetingListService.md)
 * NegativeCampaignRetargetingListService（廃止）
<br><br>

#### 2.	システムの保守、改善
以下のウェブサービスにおいてシステムの保守、改善を実施しました。<br>
対象サービスごとの変更内容は「Serviceの変更による各Versionへの影響」の項目をご確認ください。
<br>
<br>

##### 対象ウェブサービス
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)
 * [AdGroupRetargetingListService](/docs/ja/api_reference/services/AdGroupRetargetingListService.md)
<br><br>

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.6.2以前</p>
</th>
<th valign="top">
  <p>Ver.6.3</p>
</th>
</tr>
<tr>
  <td colspan="3"><b>1.	サイトリターゲティング機能の改善</b></td>
</tr>
<tr>
 <td valign="top">CampaignService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">
 ・サイトリターゲティングの配信対象ユーザー（targetAll）が設定、照会できます。
 </td>
</tr>
<tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">変更ありません。<br>
 　・専有のターゲットリストの登録、変更、照会ができます。<br>
 　・専有のサイトリターゲティング用タグを照会できます。<br>
 </td>
 <td valign="top">サイトリターゲティング機能の改善に対応します。<br>
 　・専有、および共有のターゲットリストの登録、変更、照会ができます。<br>
 　・専有、および共有のサイトリターゲティング用タグを照会できます。<br>
 　・トラッキング用のターゲットリストID（targetListTrackId）を利用できます。<br>
 　・エラーコードを追加しました。
 </td>
</tr>
<tr>
 <td valign="top">NegativeCampaignRetargetingListService</td>
 <td valign="top">利用できます。</td>
 <td valign="top">利用できません。<br>※CampaignRetargetingListServiceに機能を移管します。</td>
</tr>
<tr>
 <td valign="top">CampaignRetargetingListService</td>
 <td valign="top">利用できません。</td>
 <td valign="top">利用できます（新規追加）。<br>
 ・キャンペーンに配信対象のターゲットリストを関連付けできます。<br>
 ・キャンペーンに除外対象のターゲットリストを関連付けできます。<br>
 ・エラーコードを追加しました。
 </td>
</tr>
<tr>
  <td colspan="3"><b>2.	システムの保守、改善の実施</b></td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">・getReportFieldsで「指定できる」もしくは「指定できない」の情報を照会できます。<br>
 ・組み合わせ指定できないレポートフィールドフィールドを照会できます。
 </td>
</tr>
<tr>
 <td valign="top">ReportService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">getでreportName(ReportDefintionService/addで指定)を照会できます。</td>
</tr>
<tr>
 <td valign="top">AccountService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">AccountStatusに「CANCELED(解約済み)」を新規公開しました。<br>これにより解約済みアカウントを照会できます。</td>
</tr>
<tr>
 <td valign="top">AdGroupRetargetingListService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">エラーコードを追加しました。<br>仕様に変更はありません。</td>
</tr>
</table>
