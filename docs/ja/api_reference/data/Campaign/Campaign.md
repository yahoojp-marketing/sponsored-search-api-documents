# Campaign
Campaignオブジェクトは、キャンペーンの情報を表します。

### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

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
  <td>Ignore</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>Requirement<br><i>NotUpdatable</i></td>
 </tr>
 <tr>
  <td>campaignTrackId</td>
  <td>xsd:long</td>
  <td>トラッキング用キャンペーンIDです。<br>※Sandbox環境では常に0が返ります。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名です。<br>※入力制限：50文字以内です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatuses</td>
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>ユーザーにより広告配信の有無を調整できる設定です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>servingStatus</td>
  <td>enum <a href="CampaignServingStatus.md">CampaignServingStatus</a></td>
  <td>キャンペーンレベルの配信状況です。<br>ユーザーによる広告配信の調整に関わらず、キャンペーンとしての状態を表します。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>キャンペーンの開始日です。<br>過去の日付は指定できません。<br>※配信開始済みのキャンペーンは変更できません。</td>
  <td>yes</td>
  <td>Optional<br>※Default: 当日日付</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>キャンペーンの終了日です。<br>過去の日付、開始日以前の日付は指定できません。</td>
  <td>yes</td>
  <td>Optional<br>※Default: 20371231</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>budget</td>
  <td><a href="Budget.md">Budget</a></td>
  <td>キャンペーンの予算です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyConfiguration</td>
  <td><a href="CampaignBiddingStrategy.md">CampaignBiddingStrategy</a></td>
  <td>入札設定です。<br>※BudgetOptimizerは設定できません。<br>※アプリキャンペーンでiOSを指定した場合、TARGET_CPA/TARGET_ROASは 設定できません。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>biddingStrategyFailedReason</td>
  <td>enum <a href="BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a></td>
  <td>自動入札の設定に失敗した理由です。<br>※失敗時のみレスポンスとして表示されます。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>failedBiddingStrategyConfiguration</td>
  <td><a href="CampaignBiddingStrategy.md">CampaignBiddingStrategy</a></td>
  <td>登録に失敗した自動入札設定です。<br>※失敗時のみレスポンスとして表示されます。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionOptimizerEligibility</td>
  <td>enum <a href="ConversionOptimizerEligibility.md">ConversionOptimizerEligibility</a></td>
  <td>コンバージョンオプティマイザーが利用可能であるか判定します。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adServingOptimizationStatus</td>
  <td>enum <a href="AdServingOptimizationStatus.md">AdServingOptimizationStatus</a></td>
  <td>広告表示の最適化の設定です。<br>※キャンペーンの「広告表示の最適化」項目は読み取り専用になりました。</td>
  <td>yes</td>
  <td>Ignore<br>※default値「OPTIMIZE」が設定されます。<br>任意の値は設定できません。</td>
  <td>Ignore<br>※設定済みの値がレスポンスされます。<br>任意の値には変更できません。</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>settings[0..3]</td>
  <td>
  <a href="CampaignSettings.md">CampaignSettings</a><br>
  inherited <a href="GeoTargetTypeSetting.md">GeoTargetTypeSetting</a><br>
  inherited <a href="TargetingSetting.md">TargetingSetting</a><br>
  inherited <a href="DynamicAdsForSearchSetting.md">DynamicAdsForSearchSetting</a>
  </td>
  <td>ターゲティング、およびマッチング設定です。</td>
  <td>yes</td>
  <td>Optional<br>
  ※TargetingSettingが未設定の場合のDefault値<br>
  SettingType:TARGET_LIST_SETTING<br>
  TargetAll:ACTIVE</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignType</td>
  <td>enum <a href="CampaignType.md">CampaignType</a></td>
  <td>キャンペーンの種類です。</td>
  <td>yes</td>
  <td>Optional<br>※Default: STANDARD</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appStore</td>
  <td>enum <a href="AppStore.md">AppStore</a></td>
  <td>アプリストアの選択です。</td>
  <td>yes</td>
  <td>campaignTypeがSTANDARDの場合:ignore<br>
   campaignTypeがMOBILE_APPの場合:Requirement<br>
   campaignTypeがDYNAMIC_ADS_FOR_SEARCH_SETTINGの場合:ignore
  </td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appId</td>
  <td>xsd:string</td>
  <td>アプリID（iOS）またはパッケージ名（Android）です。<br>※アプリキャンペーンでiOSの場合、入力は数値のみです。</td>
  <td>yes</td>
  <td>campaignTypeがSTANDARDの場合:ignore<br>
   campaignTypeがMOBILE_APPの場合:Requirement
   campaignTypeがDYNAMIC_ADS_FOR_SEARCH_SETTINGの場合:ignore
  </td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>トラッキングURLです。<br>※アプリキャンペーンでAndroidの場合、設定はできません。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>※こちらが審査中の場合、編集はできません。<br>※変更がない場合、審査対象とはなりません。</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="CustomParameters.md">CustomParameters</a></td>
  <td>カスタムパラメータです。<br>※アプリキャンペーンでAndroidの場合、設定はできません。</td>
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
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
