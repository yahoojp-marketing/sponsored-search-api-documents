# リリースノート
スポンサードサーチAPI V201808

## リリースバージョン
V201808（WSDLバージョン V201808）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. 動的検索連動型広告への対応
動的検索連動型広告は、あらかじめ指定したウェブサイトのコンテンツと関連性の高い検索キーワードに対して、広告のタイトルを自動生成して配信する広告です。
スポンサードサーチAPIでは主に以下の対応を実施しました。

1. 動的検索連動型広告やページフィードの入稿などに対応しました。
1. 動的検索連動型広告関連の以下のレポートタイプを追加しました。<br>
‐検索クエリーレポート（動的検索連動型広告）<br>
‐ページフィードターゲティングレポート<br>
※レポートフィールド一覧は[こちら](/docs/ja/api_reference/appendix/reportfields.md)からご確認ください。

##### 対象ウェブサービス
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [FeedFolderService](/docs/ja/api_reference/services/FeedFolderService.md)
 * [PageFeedItemService](/docs/ja/api_reference/services/PageFeedItemService.md)
 * [CampaignWebpageService](/docs/ja/api_reference/services/CampaignWebpageService.md)
 * [AdGroupWebpageService](/docs/ja/api_reference/services/AdGroupWebpageService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)

### 2. デバイスをまたいだコンバージョン測定の設定値を変更
ConversionTrackerServiceにおけるCrossDeviceConversionFlag（デバイスをまたいだコンバージョンの計測を制御するフラグ）設定時の挙動を以下のとおり変更しました。<br>
これによりコンバージョン測定の新規作成、および更新時のCrossDeviceConversionFlagの値は「TRUE」のみ設定可能となりました。

* 新規作成時(ADD)<br>
値の設定有無にかかわらず、「TRUE」がレスポンスされます。
* 更新時(SET)<br>
値が設定されている場合、値の内容にかかわらず「TRUE」がレスポンスされます（設定した値がIgnoreとして扱われます）。

※本変更は下位のバージョン（Ver.6.5.0、およびV201805）にも適用されます。

##### 対象ウェブサービス
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)

### 3. 「コンバージョン数を最大化」に替わる新しい自動入札タイプへの対応
自動入札設定機能におけるENHANCED_CPC（コンバージョン数を最大化）について、以下の変更を予定しております。

* ENHANCED_CPCの提供終了
* ENHANCED_CPCに替わる新しい自動入札タイプの提供

V201808では新しい自動入札タイプの提供に対応するため、インターフェースの変更を行います。
詳細な変更内容は「Serviceの変更による各Versionへの影響」の項目をご確認ください。 

##### 補足
* インターフェースのみの変更となるため、V201808リリース時点では新しい自動入札タイプの設定はできません。
* ENHANCED_CPCの提供終了日程や、新しい自動入札タイプの提供開始に関する詳細は、決まり次第お知らせいたします。
* ENHANCED_CPCはV201808リリース後も、一定期間は引き続きご利用いただけます。
  
##### 対象ウェブサービス
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)

### 4. サイトリターゲティング 訪問履歴の有効期間の最大値を拡張
ターゲットリストに設定可能な有効期間（蓄積された訪問履歴をターゲティング対象として有効とする期間）の最大日数が以下のとおり変更になりました。<br>
（変更前）180日→（変更後）540日

※初期値は180日から変更ありません。<br>
※本変更は下位のバージョン（Ver.6.5.0、およびV201805）にも適用されます。

##### 対象ウェブサービス
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

### 5. システムの保守、改善
システムの保守、改善として以下を実施しました。

* 一部のエラーコードについて構成を見直し、整理しました。<br>
詳細は「[エラーコードの再編について](/docs/ja/api_reference/appendix/error_codes_structure.md)」をご確認ください。
* キーワード候補提案機能の精度改善を行いました。<br>
これに伴いTargetingIdeaServiceの検索条件にaccountIdを必須項目として追加しました。<br>
<br>
※「Serviceの変更による各Versionへの影響」の項目もあわせてご確認ください。 

##### 対象ウェブサービス 
 * 全サービス（エラーコードに関する変更）
 * [TargetingIdeaService](/docs/ja/api_reference/services/TargetingIdeaService.md)

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
V201805以前
</th>
<th>
V201808
</th>
</tr>
<tr>
 <td valign="top">CampaignService</td>
 <td valign="top">インターフェースに変更はありません。<br>
  ※DYNAMIC_ADS_FOR_SEARCH（動的検索連動型広告キャンペーン）は削除のみ可能です。<br>
  ※入札方法の設定に変更はありません。
 </td>
 <td valign="top">
  ・DYNAMIC_ADS_FOR_SEARCH（動的検索連動型広告キャンペーン）について以下の操作が可能になりました。<br>
  　‐参照<br>
  　‐追加<br>
  　‐更新<br>
  　‐削除<br>
  ・入札方法の設定が以下のとおり変更になります。<br>
  　‐入札方法に「コンバージョン数の最大化」に替わる新しい自動入札タイプを設定する場合（新しい自動入札タイプの提供開始後より有効）<br>
    biddingStrategyType（入札方法）にMANUAL_CPCを設定し、かつenhancedCpcEnabledに「TRUE」を設定する。<br>
  　‐手動入札を設定する場合<br>
  　biddingStrategyType（入札方法）にMANUAL_CPCを設定し、かつenhancedCpcEnabledを未設定、または「FALSE」を設定する。<br><br>
  ※biddingScheme項目を未設定でリクエストした場合は、enhancedCpcEnabledは「FALSE」でレスポンスされます。<br>
  ※従来のENHANCED_CPC（コンバージョン数を最大化）も一定期間は引き続きご利用いただけます。
</td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">インターフェースに変更はありません。<br>
  ※DYNAMIC_SEARCH_LINKED_AD（動的検索連動型広告）は削除のみ可能です。
 </td>
 <td valign="top">
  ・AdType（広告タイプ）にDYNAMIC_SEARCH_LINKED_AD（動的検索連動型広告）を追加しました。<br>
  ・DYNAMIC_SEARCH_LINKED_AD（動的検索連動型広告）について以下の操作が可能になりました。<br>
  　‐参照<br>
  　‐追加<br>
  　‐更新<br>
  　‐削除<br>
  ・クリエイティブ情報に動的検索連動型広告の情報を追加しました。
 </td>
</tr>
<tr>
 <td valign="top">FeedFolderService</td>
 <td valign="top">インターフェースに変更はありません。<br>
  ※DYNAMIC_SEARCH_LINKED_AD（動的検索連動型広告）は削除のみ可能です。
 <td valign="top">
  ・AdType（広告タイプ）にDYNAMIC_SEARCH_LINKED_AD（動的検索連動型広告）を追加しました。<br>
  ・クリエイティブ情報に動的検索連動型広告の情報を追加しました。
</td>
</tr>
<tr>
 <td valign="top">PageFeedItemService</td>
 <td valign="top">本サービスは未提供です。</td>
 <td valign="top">
  ページフィードアイテムについて以下の操作が可能になりました。<br>
  　-アップロード<br>
  　-ダウンロード<br>
  　-サマリー情報の取得<br>
</td>
</tr>
<tr>
 <td valign="top">CampaignWebpageService</td>
 <td valign="top">本サービスは未提供です。</td>
 <td valign="top">
  キャンペーンにおけるページフィードの除外設定について、以下の操作が可能になりました。<br>
  　-参照<br>
  　-登録<br>
  　-削除
</td>
</tr>
<tr>
 <td valign="top">AdGroupWebpageService</td>
 <td valign="top">本サービスは未提供です。</td>
 <td valign="top">
  広告グループにおけるページフィードの配信、除外設定について、以下の操作が可能になりました。<br>
  　-参照<br>
  　-登録<br>
  　-更新<br>
  　-削除
</td>
</tr>
<tr>
 <td valign="top">ConversionTrackerService</td>
 <td valign="top">インターフェースに変更はありません。<br>
 <td valign="top">
  CrossDeviceConversionFlag（デバイスをまたいだコンバージョンの計測を制御するフラグ）設定時の挙動が以下のとおり変更されました。<br>
  　‐新規作成時(ADD)<br>
  　値の設定有無にかかわらず、「TRUE」がレスポンスされます。<br>
  　‐更新時(SET)<br>
  　値が設定されている場合、値の内容にかかわらず「TRUE」がレスポンスされます（設定した値がIgnoreとして扱われます）。
</td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">インターフェースに変更はありません。<br>
  ※動的検索連動型広告に関連したレポートタイプの登録、更新、削除はできません。
 <td valign="top">
  以下のレポートタイプが追加されました。<br>
  　‐KEYWORDLESS_QUERY（検索クエリーレポート（動的検索連動型広告））<br>
  　‐WEBPAGE_CRITERION（ページフィードターゲティングレポート）
</td>
</tr>
<tr>
 <td valign="top">ReportService</td>
 <td valign="top">インターフェースに変更はありません。<br>
  ※動的検索連動型広告に関連したレポートタイプの登録、更新、削除はできません。
 <td valign="top">
  以下のレポートタイプが追加されました。<br>
  　‐KEYWORDLESS_QUERY（検索クエリーレポート（動的検索連動型広告））<br>
  　‐WEBPAGE_CRITERION（ページフィードターゲティングレポート）
</td>
</tr>
<tr>
 <td valign="top">TargetingIdeaService</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">検索条件にaccountIdを必須項目として追加しました。</td>
</tr>
<tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">インターフェースに変更はありません。<br>
 ※reachStorageSpanに指定可能な最大日数を180日→540日に変更しました。<br>
  ※Default値は180日</td>
 <td valign="top">インターフェースに変更はありません。<br>
 ※reachStorageSpanに指定可能な最大日数を180日→540日に変更しました。<br>
  ※Default値は180日</td>
</tr>
<tr>
 <td valign="top">全サービス</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">一部のエラーコードについて、構成を見直し整理しました。</td>
</tr>
</table>

## スポンサードサーチAPI Ver.6.5の提供終了について
以下の日程でスポンサードサーチAPI Ver.6.5のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2018年9月10日（月）<br>
* システム終了日：2018年12月10日（月）<br>
