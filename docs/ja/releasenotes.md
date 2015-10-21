# リリースノート
スポンサードサーチAPI ver.5.3
## リリースバージョン
5.3 (WSDLバージョン: 5.3.0)
## バージョンアップの種類
マイナーバージョンアップ  
※バージョンアップの種類についてはこちらをご確認ください。
## 本リリースの主な内容

#### 1. サイトリターゲティングの提供
サイトリターゲティング機能の提供を行いました。概要については以下のページよりご確認ください。<br>
http://promotionalads.yahoo.co.jp/support/release/2015/0902.html<br>
機能詳細は以下のとおりです。<br>
・各種ターゲットリストの作成、変更、照会機能を追加しました。ターゲットリストは以下のとおりです：<br>
　- デフォルトリスト（リタゲのタグの発行ができるようになりました）<br>
　- 条件リスト<br>
　- 組み合わせリスト<br>
・ターゲットリストをキャンペーンや広告グループへ配信対象/除外対象の設定ができるようになりました。<br>
※キャンペーンは除外対象のみ設定が可能です。<br>
・レポート種別にリターゲティング配信を追加しました。<br>
・ターゲットリストの操作履歴を照会できるようになりました。<br>

* 対象ウェブサービス  
 * [AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)
 * [NegativeCampaignRetargetingListService](/docs/ja/api_reference/services/NegativeCampaignRetargetingListService.md)
 * [AdGroupRetargetingListService](/docs/ja/api_reference/services/AdGroupRetargetingListService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [CustomerSyncService](/docs/ja/api_reference/services/AdGroupService.md)

* 対象データオブジェクト  
 * データオブジェクト集をご確認ください。
  
* 対象Enumerations  
 * Enumeration集をご確認ください。
  
#### 2. アプリダウンロードキャンペーンの提供
アプリダウンロードキャンペーン機能の提供を行いました。機能詳細は以下のとおりです。<br>
・アプリダウンロード広告用のキャンペーンが作成できます。<br>
・アプリの各種コンバージョントラッキングに以下が追加されました。<br>
　- アプリ初回起動コンバージョン<br>
　- アプリ内行動コンバージョン<br>
・キャンペーンレポートにキャンペーンタイプ項目を追加しました。また、レポート作成には以下のような制約があります。<br>
　- リンク先URLレポートを作成できません。<br>
　- 検索クエリレポートでは、リンク先URLを指定しても値なしで戻ります。<br>
※現在のキャンペーンは「標準キャンペーン」と名称変更されます。<br>
※標準キャンペーンに作成されているアプリダウンロード広告は2015年12月中旬以降、配信されなくなる可能性があります。<br>
　該当の広告を運用されているパートナー様はアプリダウンロードキャンペーンへの移行をお願いします。<br>
  
* 対象ウェブサービス
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)

* 対象データオブジェクト  
 * データオブジェクト集をご確認ください。
  
* 対象Enumerations  
 * Enumeration集をご確認ください。

#### 3.	保守改善の追加
一部機能の保守改善を行いました。詳細は以下のとおりです。<br>
・データ自動挿入の操作履歴が追加されました。<br>
・1リクエストで複数キャンペーンの広告グループ操作ができるようになりました。<br>
・1リクエストの操作上限を引き上げました。<br>
  
* 対象ウェブサービス
 * [CustomerSyncService](/docs/ja/api_reference/services/CustomerSyncService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)

* 対象データオブジェクト  
 * データオブジェクト集をご確認ください。
  
* 対象Enumerations  
 * Enumeration集をご確認ください。

#### 4. Serviceの変更による各Versionへの影響

<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.5.2以前</p>
</th>
<th valign="top">
  <p>Ver.5.3</p>
</th>
 </tr>
 <tr>
 <td valign="top">
  <p>RetargetingListService</p>
</td>
<td valign="top">
  <p>・機能提供はありません。</p>
</td>
<td valign="top">
  <p>・新規公開です。</p>
</td>
</tr>
 <tr>
 <td valign="top">
  <p>NegativeCampaign<br>RetargetingListService</p>
</td>
<td valign="top">
  <p>・機能提供はありません。</p>
</td>
<td valign="top">
  <p>・新規公開です。</p>
</td>
</tr>
 <tr>
 <td valign="top">
  <p>AdGroupRetargeting<br>ListService</p>
</td>
<td valign="top">
  <p>・機能提供はありません。</p>
</td>
<td valign="top">
  <p>・新規公開です。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupService</p>
</td>
<td valign="top">
  <p>・iOSのアプリダウンロードキャンペーンにはコンバージョン（TARGET_CPA、TARGET_ROAS）の入札戦略は指定できません。<br>
・ターゲット設定の追加フィールドの参照、更新、削除ができません。</p>
</td>
<td valign="top">
  <p>・広告グループ（AdGroup）にターゲットを設定するフィールド（settings）を追加しました。<br>
・ターゲットタイプ（Settings）、ターゲット設定（TargetingSetting）エンティティを追加しました。<br>
・クライテリア種別（Criterion Type）、ターゲットの絞り込み設定（TargetAll）を追加しました。<br>
・更新と参照上限を変更しました。<br>
・iOSのアプリダウンロードキャンペーンにコンバージョン（TARGET_CPA、TARGET_ROAS）の入札戦略は指定できません。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>ReportDefinitionService</p>
</td>
<td valign="top">
  <p>・レポート定義にターゲットリストIDを設定できません。<br>
・レポートタイプにターゲットリストを指定できません。</p>
</td>
<td valign="top">
  <p>・レポート定義（ReportDefinition）にターゲットリストIDを設定するフィールド（targetListIds）を追加しました。<br>
・レポートタイプ（ReportType）にターゲットリストを追加しました。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CustomerSyncService</p>
</td>
<td valign="top">
  <p>・エンティティ種別にターゲットリスト、データ自動挿入用の値を指定できません。<br>
・ターゲットリスト、データ自動挿入の照会はできません。</p>
</td>
<td valign="top">
  <p>・操作履歴（Auditlog）のフィールドにリターゲティング用（targetList Id）、データ自動挿入（feedFolderId）を追加しました。<br>
・エンティティ種別（EntityType）にターゲットリスト、データ自動挿入用の値を追加しました。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignService</p>
</td>
<td valign="top">
  <p>・アプリダウンロードキャンペーンの作成はできません。<br>
※Ver.5.3で追加された項目も参照できません。<br>
・iOSのアプリダウンロードキャンペーンにコンバージョン（TARGET_CPA、TARGET_ ROAS）の入札戦略は指定できません。</p>
</td>
<td valign="top">
  <p>・キャンペーン（Campaign）にアプリダウンロードキャンペーンの項目（campaignType、appStore、appId）を追加しました。<br>
・キャンペーンタイプ（CampaignType）、アプリストアタイプ（AppStore）設定を追加しました。<br>
・更新と参照上限を変更しました。<br>
・iOSのアプリダウンロードキャンペーンにコンバージョン（TARGET _CPA、TARGET_ ROAS）の入札戦略は指定できません。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupAdService</p>
</td>
<td valign="top">
  <p>・標準キャンペーンにアプリダウンロード広告の登録はできません。</p>
</td>
<td valign="top">
  <p>・標準キャンペーンにアプリダウンロード広告の作成はできません。<br>
・アプリダウンロードキャンペーンにテキスト広告の作成はできません。<br>
・アプリダウンロードキャンペーンの場合、アプリストアとアプリIDは自動設定されます。<br>
・Androidのアプリダウンロードキャンペーンの場合、リンク先URLは設定されても無視されます。<br>
・参照上限を変更しました。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>ConversionTrackerService</p>
</td>
<td valign="top">
  <p>・ウェブコンバージョン（Web Conversion）にある通信プロトコル（httpProtocol）の更新ができません。</p>
</td>
<td valign="top">
  <p>・ウェブコンバージョン（Web Conversion）にある通信プロトコル（httpProtocol）の設定が不要になりました。<br>
・アプリコンバージョントラッカー（AppConversion）にコンバージョンの入力情報（snippetId、snippet Label、appPostbackUrl）を追加しました。<br>
・アプリダウンロードコンバージョン種別（AppConversionType）にアプリ内行動、アプリ初回起動の項目を追加しました。<br>
・アプリポストバックURLのクリアフラグ（AppPostBackUrl）を追加しました。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupCriterionService</p>
</td>
<td valign="top">
  <p>・Androidのアプリダウンロードキャンペーンの場合、カスタムURLは設定されても無視されます。</p>
</td>
<td valign="top">
  <p>・Androidのアプリダウンロードキャンペーンの場合、カスタムURLは設定されても無視されます。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>FeedItemService</p>
</td>
<td valign="top">
  <p>・アプリダウンロードキャンペーンにはデータ自動挿入を紐付けできません。<br>
※Ver.5.2の場合。</p>
</td>
<td valign="top">
  <p>・アプリダウンロードキャンペーンにはデータ自動挿入を紐付けできません。<br>
※本ServiceではEntityやEnumに変更はありません。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignFeedService</p>
</td>
<td valign="top">
  <p>・アプリダウンロードキャンペーンにはクイックリンクオプション、または電話番号オプションを紐付けできません。</p>
</td>
<td valign="top">
  <p>・アプリダウンロードキャンペーンにはクイックリンクオプション、または電話番号オプションを紐付けできません。<br>
※本ServiceではEntityやEnumに変更はありません。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupFeedService</p>
</td>
<td valign="top">
  <p>・アプリダウンロードキャンペーンにはクイックリンクオプション、または電話番号オプションを紐付けできません。</p>
</td>
<td valign="top">
  <p>・アプリダウンロードキャンペーンにはクイックリンクオプション、または電話番号オプションを紐付けできません。<br>
※本ServiceではEntityやEnumに変更はありません。</p>
</td>
</tr>
</tbody>
</table>

## スポンサードサーチAPI Ver.5.0とVer.5.1のサポート終了予定日
スポンサードサーチAPI Ver.5.0は、2015年10月30日（金）にサポート終了予定です。<br>
スポンサードサーチAPI Ver.5.1は、2016年3月末以降にサポート終了予定です。（※）<br>
※決定次第、あらためてお知らせいたします。<br>

