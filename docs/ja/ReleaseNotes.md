# リリースノート
スポンサードサーチAPI Ver.6.0

## リリースバージョン
6.0 (WSDLバージョン: 6.0.0)

## バージョンアップの種類
メジャーバージョンアップ  

## 本リリースの主な内容

#### 1. アドバンスドURLの提供
リンク先URLやカスタムURL管理の利便性向上のためにアドバンスドURLを提供いたします。<br>
詳細は以下のとおりです。

##### URLの設定
* 以下のServiceにトラッキングURLの設定が可能になります。<br>
　※トラッキングURLは審査対象のため、審査ステータス、審査否認理由コード、審査中または否認されたトラッキングURLの取得が可能になります。<br>
　・AccountTrackingUrlService<br>
　・CampaignService<br>
　・AdGroupService<br>
　・AdGroupAdService<br>
　・AdGroupCriterionService<br>
　・FeedItemService<br>
* 以下のトラッキング用IDの取得が可能になります。<br>
　・CampaignID<br>
　・AdGroupID<br>
　・AdGroupCriterionID<br>
　・FeedItemID<br>
　・RetargetingListID<br>
* 以下のServiceにカスタムパラメータの設定が可能になります。<br>
　・CampaignService<br>
　・AdGroupAdService<br>
　・AdGroupCriterionService<br>
　・AdGroupService<br>
　・FeedItemService<br>
* 以下のServiceは、リンク先URLが最終リンク先URLとなります。<br>
※移行期間中は、既存のリンク先URL（アドバンスURL移行前）の設定が可能です。<br>
　・AdGroupAdService<br>
　・AdGroupCriterionService<br>
　・FeedItemService<br>
* 以下のトラッキングパラメータが追加されます。<br>
　・lpurl：最終リンク先URLを取得できます。トラッキングURLのみ有効です。<br>

##### レポートの提供と変更
* 最終リンク先URLレポートが提供されます。<br>
* リンク先URLレポートが削除されます。（2016年1月13日（水）に削除済み）<br>
* 最終リンク先URLが以下のレポートフィールドとして追加されます。<br>
　・広告レポート<br>
　・キーワードレポート<br>
　・広告表示オプションレポート<br>
* トラッキングURL、カスタムパラメータが以下のレポートフィールドとして追加されます。<br>
　・アカウントレポート※<br>
　・キャンペーンレポート<br>
　・広告グループレポート<br>
　・広告レポート<br>
　・キーワードレポート<br>
　・広告表示オプションレポート<br>
　※トラッキングURLのみ追加されます。

##### その他
* 文字の算出方法が変更されます。<br>
　対象項目は以下のとおりです。<br>
　・広告（Ad）<br>
　　・タイトル文（headline）<br>
　　・説明文（description）<br>
　　・説明文2（description2）<br>
　　・表示URL（displayURL）<br>
　・フィードアイテム（FeedItem）<br>
　　・リンクテキスト<br>
* URLの設定が変更されます。<br>
　・日本語ドメインの利用が可能になります。<br>
　・すべてのトップレベルドメイン（TLD）の利用が可能になります。<br>
　※ただし、すべてのドメインが審査対象となります。<br>
* BulkServiceを廃止します。
<br><br>

##### 対象ウェブサービス  
 * [AccountTrackingUrlService](/docs/ja/api_reference/services/AccountTrackingUrlService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)
 * BulkService（廃止）
<br><br>

##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

#### 2. レポート機能の改善
レポート機能の変更および追加を行います。<br>
変更内容は以下のとおりです：
* レポート項目（フィールド）の組み合わせにより、セグメントを自動判別して作成するように変更されます。<br>
※前バージョンまで提供していた機能は、本バージョンからご利用いただけません。<br>
※本バージョンのレポートへ移行する際、前バージョンで登録されているレポート定義やレポートジョブは引き継がれません。
* フィルターで指定するコード値は、レポートで表示される項目を指定するようになります。<br>
* レポートのダウンロードURL取得（ReportServiceのgetDownloadUrl）操作を廃止いたします。<br>
※本バージョンから、ダウンロードURLは取得（ReportServiceのget）操作より取得が可能になります。<br>
* 「総コンバージョン数」フィールドの型がlongからdoubleに変更されます。<br>
<br>

また、本変更に伴い、以下の点を変更いたしました。<br>
* 日付表記をYYYY-MM-DD（-区切り）に統一しました。<br>
* データが空の項目についての表示を「--」（ハイフン2個連続表示）に変更しました。<br>
* レポートファイルの1行目から5行目に固定で表示されていた以下の情報を削除しました。<br>
　・アカウント名（アカウントID）<br>
　・レポート名（レポートの種類）<br>
　・集計期間<br>
　・表示切替<br>
　・フィルター設定<br>
* 以下のフィールド値について、0の場合の表記を0.000に変更しました。<br>
　・AVG_CPC<br>
　・AVG_CPM<br>
　・BUDGET_LOST_IMPRESSION_SHARE<br>
　・CLICK_RATE<br>
　・CONVERSION<br>
　・CONVERSION_RATE<br>
　・COST_UNIQUE_CONVERSION<br>
　・CPA<br>
　・EXACT_MATCH_IMPRESSION_SHARE<br>
　・INVALID_CLICK_RATE<br>
　・IMPRESSION_SHARE<br>
　・QUALITY_LOST_IMPRESSION_SHARE<br>
　・REVENUE_CONVERSION<br>
　・REVENUE_UNIQUE_CONVERSION<br>
　・REVENUE<br>
　・UNIQUE_CONVERSION_RATE<br>
<br>

##### 対象ウェブサービス
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
<br><br>

##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

#### 3.	保守改善の追加
一部機能の保守改善を行います。<br>
改善内容は以下のとおりです：<br>
* キーワード提案サービスに除外キーワードによる設定機能が廃止されます。<br>
* エクスポート機能が提供されます。（※）<br>
　キャンペーン、広告グループ、キーワード、広告に関する情報の取得を一括で行えます。<br>
　※4月13日以降にリリース予定です。
<br><br>

##### 対象ウェブサービス
 * [TargetingIdeaService](/docs/ja/api_reference/services/TargetingIdeaService.md)
 * [CampaignExportService](/docs/ja/api_reference/services/CampaignExportService.md)
<br><br>

##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.5.3以前</p>
</th>
<th valign="top">
  <p>Ver.6.0</p>
</th>
</tr>
<tr>
  <td colspan="3"><b>アドバンスドURLの提供</b></td>
</tr>
<tr>
 <td valign="top">
  <p>AccountTrackingUrlService</p>
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
  <p>AdGroupAdService</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除は できません。<br>
　・最終リンク先URL<br>
　・最終リンク先URL （スマートフォン）<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・アドバンスドURLの移行後は、広告（Ad）の取得はできません。<br>
・文字の算出方法が変更されます（Ver.5.2、Ver.5.3のみ）。<br>
・URL設定が変更されます（Ver.5.2、Ver.5.3のみ）。</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除が可能に なります。<br>
　・最終リンク先URL<br>
　・最終リンク先URL （スマートフォン）<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・文字の算出方法が変更されます。<br>
・URL設定が変更されます。</p>
</td>
</tr>
 <tr>
 <td valign="top">
  <p>AdGroupCriterionService</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除は できません。<br>
　・最終リンク先URL<br>
　・最終リンク先URL （スマートフォン）<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得はできません。<br>
・アドバンスドURLの移行後は、キーワード （Keyword）の取得はできません。<br>
・URL設定が変更されます（Ver.5.2、Ver.5.3のみ）。</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除が可能に なります。<br>
　・最終リンク先URL<br>
　・最終リンク先URL （スマートフォン）<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得が可能になります。<br>
・URL設定が変更されます。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>AdGroupService</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除は できません。<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得はできません。<br>
・アドバンスドURLの移行後は、広告グループ （AdGroup）の取得は できません。</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除が可能に なります。<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得が可能になります。<br>
</td>
</tr>
<tr>
<td valign="top">
  <p>BulkService</p>
</td>
<td valign="top">
  <p>・変更はありません。</p>
</td>
<td valign="top">
  <p>・Serviceが廃止されます。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignService</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除は できません。<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得はできません。<br>
・アドバンスドURLの移行後は、キャン ペーン（Campaign）の取得はできません。</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除が可能に なります。<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得が可能になります。<br>
・類似キーワードマッチング設定機能（KeywordMatchSetting）が廃止されます。
</td>
</tr>
<tr>
<td valign="top">
  <p>FeedItemService</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除は できません。<br>
　・最終リンク先URL<br>
　・最終リンク先URL （スマートフォン）<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得はできません。<br>
・アドバンスドURLの移行後は、フィードアイテム （FeedItem）の取得は できません。<br>
・文字の算出方法が変更されます（Ver.5.2、Ver.5.3のみ）。<br>
・URL設定が変更されます（Ver.5.2、Ver.5.3のみ）。</p>
</td>
<td valign="top">
  <p>・以下の取得/追加/変更/削除が可能に なります。<br>
　・最終リンク先URL<br>
　・最終リンク先URL （スマートフォン）<br>
　・トラッキングURL<br>
　・カスタムパラメータ<br>
・トラッキング用IDの取得が可能になります。<br>
・文字の算出方法が変更されます。<br>
・URL設定が変更されます。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>RetargetingListService</p>
</td>
<td valign="top">
  <p>・トラッキング用IDの取得はできません。</p>
</td>
<td valign="top">
  <p>・トラッキング用IDの取得が可能になります。</p>
</td>
</tr>
<tr>
  <td colspan="3"><b>レポート機能の改善</b></td>
</tr>
<tr>
<td valign="top">
  <p>ReportDefinitionService</p>
</td>
<td valign="top">
  <p>・変更はありません。<br>
・リンク先URLレポートが 廃止されます。</p>
</td>
<td valign="top">
  <p>・変更（set）操作が廃止されます。<br>
・セグメント選択が廃止されます。<br>
・新規のレポートタイプを追加します。<br>
・既存レポートで指定できるフィールドを 追加します。<br>
・リンク先URLレポートが廃止されます。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>ReportService</p>
</td>
<td valign="top">
  <p>・変更はありません。</p>
</td>
<td valign="top">
  <p>・getDownloadUrl操作が廃止されます。<br>
  ※ダウンロードURLは取得（get）操作 より取得が可能になります。</p>
</td>
</tr>
<tr>
  <td colspan="3"><b>保守改善の追加</b></td>
</tr>
<tr>
<td valign="top">
  <p>TargetingIdeaService</p>
</td>
<td valign="top">
  <p>・変更はありません。</p>
</td>
<td valign="top">
  <p>・除外キーワードの設定機能 （ExcludedKeywordSearchParameter）が削除されます。</p>
</td>
</tr>
<tr>
<td valign="top">
  <p>CampaignExportService</p>
</td>
<td valign="top">
  <p>・機能提供はありません。</p>
</td>
<td valign="top">
  <p>・新規公開です。</p>
</td>
</tr>
</tbody>
</table>

## スポンサードサーチAPI 過去バージョンのサポート終了予定日
* 以下のバージョンは、アドバンスドURLへの移行終了時（2016年10月頃）にサポート終了予定です。<br>
　・スポンサードサーチAPI Ver.5.1<br>
　・スポンサードサーチAPI Ver.5.2<br>
　・スポンサードサーチAPI Ver.5.3<br>
<br>

