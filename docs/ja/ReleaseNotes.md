# リリースノート
スポンサードサーチAPI V201909

## リリースバージョン
V201909（WSDLバージョン V201909）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. 広告文への商標の使用制限に対応
広告とクイックリンクオプションについて、商標の使用制限が解除されているかを一括で確認できるようになりました。<br>
商標の使用制限が解除されている場合は、「AdGroupAdService」および「FeedItemService」に制限が解除された旨の値が返却されます。<br>
広告管理ツールでは2019年5月に提供を開始しました。詳細は以下のお知らせをご覧ください。<br>
[広告文への商標の使用制限 正式提供開始のお知らせ](https://promotionalads.yahoo.co.jp/support/release/674122.html)<br>

##### 対象ウェブサービス
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)

### 2. 「検索結果ページの目標掲載位置」の削除
検索結果ページの目標掲載位置 (PageOnePromotedBiddingScheme) を削除しました。<br>
広告管理ツールでは2019年4月に提供を終了しました。詳細は以下のお知らせをご覧ください。<br>
[「検索結果ページの目標掲載位置」の提供終了およびデータの自動移行のお知らせ](https://promotionalads.yahoo.co.jp/support/release/659760.html)

##### 対象ウェブサービス
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md)

### 3. レポート指標「平均掲載順位」の削除
レポートフィールドの「AVG_DELIVER_RANK」（平均掲載順位）を削除しました。削除後の値は、一律「--」（ハイフン2つ）として取得、表示されます。<br>
また、トラッキングURLなどの新規入稿および編集時に{adposition}が利用できなくなります。入稿済みのパラメータについては{adposition}のトラッキングが不可となり、空の文字列が返ります。なお、広告配信には影響はありません。<br>
トラッキングURLの{adposition}については以下を参照してください。<br>
[トラッキングパラメータ](https://github.com/yahoojp-marketing/sponsored-search-api-documents/blob/201901/docs/ja/api_reference/appendix/tracking.md)<br>
詳細については以下のお知らせをご覧ください。<br>
[パフォーマンスデータ一部指標提供終了のお知らせ](https://promotionalads.yahoo.co.jp/support/release/713854.html)

##### 対象ウェブサービス
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

### 4. 自動入札タイプの一部設定項目の削除
自動入札の「ポートフォリオ入札設定」で設定可能な「自動入札タイプ：クリック数の最大化」（TARGET_SPEND）のうち、「spendTarget」を削除しました。
なお、下位バージョン（V201808, V201901）で「spendTarget」を設定すると、バリデーションエラーとなります。
広告管理ツールでは2019年7月25日に提供を終了しました。詳細は以下のお知らせをご覧ください。<br>
[自動入札タイプの一部設定項目終了のお知らせ](https://promotionalads.yahoo.co.jp/support/release/683185.html)

##### 対象ウェブサービス
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md)

### 5. 「ReportService」を「ReportDefinitionService」に統合
「ReportService」を「ReportDefinitionService」に統合しました。統合に伴い、定期レポートが作成できなくなります。<br>
また、2019年12月19日（木）に、下位バージョン（V201808, V201901）における定期レポートのintervalTypeをONETIMEに変更します。これにより、定期レポートの実行はすべて停止されます。<br>
詳細は以下の仕様ドキュメントをご覧ください。<br>
 * [リファレンス](https://github.com/yahoojp-marketing/sponsored-search-api-documents/blob/201909_reportdefinition/docs/ja/api_reference/services/ReportDefinitionService.md)<br>
 * [ベストプラクティス](https://github.com/yahoojp-marketing/sponsored-search-api-documents/tree/201909_reportdefinition/docs/ja/bestpractice)<br>

##### 対象ウェブサービス
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

### 6. 広告表示オプションの機能改善
 * 拡張クイックリンクの提供開始<br>
 クイックリンクオプションに説明文を表示できるようになります（拡張クイックリンク）。それに伴い、「FeedItemPlaceholderField」に
以下の項目を追加します。<br>
 ・ LINK_DESCRIPTION_1：クイックリンク説明文1<br>
 ・ LINK_DESCRIPTION_2：クイックリンク説明文2<br>
なお、クイックリンク説明文を設定する場合は、「LINK_DESCRIPTION_1」「LINK_DESCRIPTION_2」の両方に入力する必要があります。どちらか
一方だけ入力した場合はエラーとなります。<br>
 * 配信先デバイスの廃止<br>
 広告表示オプションを関連付ける際に設定する「配信先デバイス」の提供を終了します。これにより、2019年10月2日以降は、「CampaignFeed」「AdGroupFeed」
　　の「DevicePlatform」は設定できなくなります。なお、2019年12月頃に「DevicePlatform」は利用不可になる予定です。<br>
広告管理ツールでは2019年10月2日（水）のリリースを予定しております。詳細は以下のお知らせをご覧ください。<br>
 [スポンサードサーチ クイックリンクオプションの機能追加について](https://biz.marketing.yahoo.co.jp/developercenter/news/751946/)

##### 対象ウェブサービス
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)

### 7. システムの保守、改善
 * WSDL「AuditLogService」を修正しました。
 * 「LocationService」を廃止しました。
 * 「FeedItem」の検索条件に「feedFolderId」を追加しました。
 * 広告管理ツールで操作した履歴を含めた操作履歴をAPIでも取得可能になりました。
※「Serviceの変更による各Versionへの影響」の項目もあわせてご確認ください。 

##### 対象ウェブサービス 
 * [AuditLogService](/docs/ja/api_reference/services/AuditLogService.md)
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
 <tr>
 <th>Service</th>
 <th>V201901以前</th>
 <th>V201909</th>
 </tr>
 <tr>
 <td valign="top">CampaignService</td>
 <td valign="top">
 ・入札設定に「検索結果ページの目標掲載位置」（PageOnePromotedBiddingScheme）を設定すると、バリデーションエラーとなる<br>
 ・「目標予算」（spendTarget）を設定すると、バリデーションエラーとなる<br>
 </td>
 <td valign="top">
 ・入札設定から「検索結果ページの目標掲載位置」（PageOnePromotedBiddingScheme）の項目削除<br>
 ・「目標予算」（spendTarget）の項目削除<br>
 </td>
 </tr>
 <tr>
 <td valign="top">BiddingStrategyService</td>
 <td valign="top">
 ・入札設定に「検索結果ページの目標掲載位置」（PageOnePromotedBiddingScheme）を設定すると、バリデーションエラーとなる<br>
 ・「目標予算」（spendTarget）を設定すると、バリデーションエラーとなる<br>
 </td>
 <td valign="top">
 ・入札設定から「検索結果ページの目標掲載位置」（PageOnePromotedBiddingScheme）を削除<br>
 ・「目標予算」（spendTarget）の項目削除<br>
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">
 ・使用制限が解除されているか一括で確認できない<br>
 </td>
 <td valign="top">
 ・使用制限が解除されているか一括で確認できる<br>
 </td>
 </tr>
 <tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">
 ・使用制限が解除されているか一括で確認できない<br>
 ・検索条件にfeedFolderIdを指定できない<br>
 </td>
 <td valign="top">
 ・使用制限が解除されているか一括で確認できる<br>
 ・検索条件にfeedFolderIdを指定できる<br>
 </td>
 </tr>
 <tr>
 <td valign="top">AuditLogService</td>
 <td valign="top">
 ・最小値を設定するとバリデーションエラーとなる<br>
 ・広告管理ツールの操作履歴は取得できない<br>
 </td>
 <td valign="top">
 ・最小値を設定するとバリデーションエラーとなる（対象箇所が異なるだけなので、特に影響はありません）<br>
 ・広告管理ツールの操作履歴が取得可能<br>
 </td>
 </tr>
 <tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">
 ・ReportDefinitionService/ReportServiceを利用してレポートを作成<br>
 ・定期レポートの作成は可能<br>
 ・平均掲載順位を選択可能<br>
 </td>
 <td valign="top">
 ・ReportDefinitionServiceのみを利用してレポートを作成<br>
 ・定期レポートの作成は不可<br>
 ・平均掲載順位は選択可能だが、「--」と表示される<br>
 </td>
 </tr>
 <tr>
 <td valign="top">ReportService</td>
 <td valign="top">
 ・ReportDefinitionService/ReportServiceを利用してレポートを作成<br>
 ・平均掲載順位が「--」になる<br>
 </td>
 <td valign="top">
 ・ReportServiceはReportDefinitionServiceに統合
 </td>
 </tr>
 <tr>
 <td valign="top">LocationService</td>
 <td valign="top">
 ・LocationServiceの利用は任意。
 </td>
 <td valign="top">
 ・LocationServiceは廃止。
 </td>
 </tr>
</tbody>
</table>

## スポンサードサーチAPI V201808の提供終了について
以下の日程でスポンサードサーチAPI V201808のサポート、およびシステムの提供を終了いたします。
* サポート終了日：2019年10月17日（木）<br>
* システム終了日：2019年12月19日（木）<br>
