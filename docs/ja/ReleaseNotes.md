# リリースノート
スポンサードサーチAPI Ver.6.1<br>

## リリースバージョン
6.1(WSDLバージョン: 6.1.0)

## バージョンアップの種類
マイナーバージョンアップ  

## 本リリースの主な内容

#### 1. 対象外キーワードの共有機能を追加
対象外キーワードをリストにまとめて、アカウント内で共有できる機能を追加しました。<br><br>

##### 対象ウェブサービス  
 * [AccountSharedService](/docs/ja/api_reference/services/AccountSharedService.md)
 * [SharedCriterionService](/docs/ja/api_reference/services/SharedCriterionService.md)
 * [CampaignSharedSetService](/docs/ja/api_reference/services/CampaignSharedSetService.md)
<br><br>

##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

#### 2.	自動入札設定の機能追加
自動入札設定「クリック数の最大化」で、目標予算が設定可能になりました。<br>
<br>

##### 対象ウェブサービス
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md)
<br><br>

##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

#### 3.	広告表示の最適化の選択項目追加
キャンペーンの作成時に、設定情報の「広告表示の最適化」で「コンバージョン最適化」が設定可能になりました。<br>
<br>

##### 対象ウェブサービス
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
<br><br>

##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

#### 4.	最終リンク先URLの設定件数増加
広告、キーワード、クイックリンクの各最終リンク先URLが、最大10件まで設定可能になりました。これにより、A/Bテストなどのランディングページ最適化（LPO）にも対応できます。<br>
<br>

##### 対象ウェブサービス
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)


##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

#### 5.	広告表示オプションの機能追加
広告表示オプションに、説明文を補足できる「テキスト補足オプション」を追加しました。<br>
<br>

##### 対象ウェブサービス
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md)
 * [AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)
<br><br>

##### 対象データオブジェクトとEnumeration 
 * データオブジェクト（Enumeration）集をご確認ください。
<br><br>

#### 6.	保守改善の追加
一部機能の保守改善を行いました。改善内容は以下のとおりです：<br>

* オブジェクト名の変更<br>
以下のオブジェクト名を変更しました。
<table>
<tr><th>変更前</th><th>変更後</th></tr>
<tr><td rowspan="2">PlaceholderField</td><td>FeedItemPlaceholderField</td></tr>
<tr><td>FeedFolderPlaceholderField</td></tr>
<tr><td rowspan="4">PlaceholderType</td><td>FeedFolderPlaceholderType</td></tr>
<tr><td>FeedItemPlaceholderType</td></tr>
<tr><td>CampaignFeedPlaceholderType</td></tr>
<tr><td>AdGroupFeedPlaceholderType</td></tr>
<tr><td rowspan="4">BiddingStrategy</td><td>BiddingStrategy</td></tr>
<tr><td>CampaignBiddingStrategy</td></tr>
<tr><td>AdGroupBiddingStrategy</td></tr>
<tr><td>AdGroupCriterionBiddingStrategy</td></tr>
<tr><td rowspan="2">CriterionUse</td><td>CampaignCriterionUse</td></tr>
<tr><td>AdGroupCriterionUse</td></tr>
<tr><td rowspan="2">Settings</td><td>CampaignSettings</td></tr>
<tr><td>AdGroupSettings</td></tr>
</table>


* TrafficEstimatorServiceをサンセットとしました。KeywordEstimatorServiceと同機能を提供しているためです。
<br><br>


##### 対象ウェブサービス
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md)
 * [AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [FeedFolderService](/docs/ja/api_reference/services/FeedFolderService.md)
 * [CampaignCriterionService](/docs/ja/api_reference/services/CampaignCriterionService.md)
 * TrafficEstimatorService

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
  <p>Ver.6.0以前</p>
</th>
<th valign="top">
  <p>Ver.6.1</p>
</th>
</tr>
<tr>
  <td colspan="3"><b>対象外キーワードの共有機能</b></td>
</tr>
<tr>
 <td valign="top">AccountSharedService</td><td valign="top">機能提供なし</td><td valign="top">
新規公開</td>
</tr>
<tr>
<td valign="top">SharedCriterionService</td><td valign="top">機能提供なし</td><td valign="top">
新規公開</td>
</tr>
<tr>
<td valign="top">CampaignSharedSetService</td><td valign="top">機能提供なし</td><td valign="top">
新規公開</td>
</tr>
<tr>
  <td colspan="3"><b>自動入札設定の機能追加</b></td>
</tr>
<tr>
 <td valign="top">BiddingStrategyService</td><td valign="top">TargetSpend(クリック数最大化)で設定できるのはクリック単価のみ</td><td valign="top">
TargetSpend(クリック数最大化)でspendTarget(目標予算)の設定が可能</td>
</tr>
<tr>
  <td colspan="3"><b>広告標示の最適化の選択項目追加</b></td>
</tr>
<tr>
 <td valign="top">CampaignService</td><td valign="top">CONVERSION_OPTIMIZEを指定できない</td><td valign="top">
CONVERSION_OPTIMIZEを指定できる</td>
</tr>
<tr>
  <td colspan="3"><b>最終リンク先URLの設定件数増加</b></td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td><td valign="top">最終リンク先URLの追加登録、修正、削除、照会ができない</td><td valign="top">
最終リンク先URLの追加、修正、削除、照会</td>
</tr>
<tr>
 <td valign="top">FeedItemService</td><td valign="top">最終リンク先URLの追加登録、修正、削除、照会ができない</td><td valign="top">
最終リンク先URLの追加、修正、削除、照会</td>
</tr>
<tr>
 <td valign="top">AdGroupCriterionService</td><td valign="top">最終リンク先URLの追加、修正、削除、照会ができない</td><td valign="top">
最終リンク先URLの追加、修正、削除、照会</td>
</tr>
<tr>
  <td colspan="3"><b>広告表示オプションの機能追加</b></td>
</tr>
<tr>
 <td valign="top">FeedItemService</td><td valign="top">テキスト補足オプションの関連付け、照会ができない</td><td valign="top">テキスト補足オプションの関連付け、照会</td>
</tr>
<tr>
 <td valign="top">CampaignFeedService</td><td valign="top">テキスト補足オプションの関連付け、照会ができない</td><td valign="top">テキスト補足オプションの関連付け、照会</td>
</tr>
<tr>
 <td valign="top">AdGroupFeedService</td><td valign="top">テキスト補足オプションの関連付け、照会ができない</td><td valign="top">テキスト補足オプションの関連付け、照会</td>
</tr>

<tr>
  <td colspan="3"><b>保守改善の追加</b></td>
</tr>
<tr>
 <td valign="top">FeedItemService</td><td valign="top">影響なし</td><td valign="top">Enumの名称変更</td>
</tr>
<tr>
 <td valign="top">AdGroupCriterionService</td><td valign="top">影響なし</td><td valign="top">Enumの名称変更</td>
</tr>
<tr>
 <td valign="top">CampaignFeedService</td><td valign="top">影響なし</td><td valign="top">Enumの名称変更</td>
</tr>
<tr>
 <td valign="top">AdGroupFeedService</td><td valign="top">影響なし</td><td valign="top">Enumの名称変更</td>
</tr>
<tr>
 <td valign="top">AdGroupService</td><td valign="top">影響なし</td><td valign="top">Enum、Entityの名称変更</td>
</tr>
<tr>
 <td valign="top">CampaignCriterionService</td><td valign="top">影響なし</td><td valign="top">Enumの名称変更、Entityの構成変更</td>
</tr>
<tr>
 <td valign="top">FeedFolderService</td><td valign="top">影響なし</td><td valign="top">Enumの名称変更</td>
</tr>
<tr>
 <td valign="top">TrafficEstimatorService</td><td valign="top">影響なし</td><td valign="top">削除</td>
</tr>

</table>

## スポンサードサーチAPI 過去バージョンのサポート終了予定日
* 以下のバージョンは、アドバンスドURLへの移行終了時（2016年10月頃）にサポート終了予定です。<br>
　・スポンサードサーチAPI Ver.5.1<br>
　・スポンサードサーチAPI Ver.5.2<br>
　・スポンサードサーチAPI Ver.5.3<br>
<br>
