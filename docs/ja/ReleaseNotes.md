# リリースノート
スポンサードサーチAPI V201805

## リリースバージョン
V201805（WSDLバージョン V201805）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. システムリリースの定期化とバージョン体系の変更
#### （1）システムリリースの定期化
システムリリースのスケジュールを定期化し、以下の変更を行いました。

（これまで）
* リリースタイミング<br>
機能のリリースごとに、新バージョンをリリース
* バージョン体系<br>
VX.X（例：V6.5）

（V201805以降）
* リリースタイミング<br>
一定期間ごとに機能をまとめて、新バージョンをリリース<br>
※新しいバージョンをリリースするタイミングで、現在公開中のうち最も古いバージョンのサポート終了日をお知らせします。
* バージョン体系<br>
VYYYYMM（例：V201805）

#### （2）バージョン体系の変更
一部の環境において、自動生成によりEntityが重複してしまう問題を解消するため、NameSpaceを細分化しオブジェクトの構成を変更いたしました。

※詳細は「[バージョン体系とwsdlの構成変更について](/docs/ja/api_reference/appendix/numbering_new_versions.md)」をご確認ください。

### 2. カテゴリ補足オプションの提供
スポンサードサーチAPIにおいて、広告表示オプションの新機能として、カテゴリ補足オプションを追加しました。<br>
カテゴリ補足オプションでは、商品やサービスの特性に合わせた補足カテゴリー（小見出し）と補足内容（語句）を、広告に追加できます。<br>

1. カテゴリ補足オプションの追加により、以下に対応しました。<br>
‐カテゴリ補足オプションの作成、編集、削除、および設定の参照<br>
‐キャンペーン、広告グループへの関連付け設定、解除、設定の参照<br>
‐操作履歴の取得
1. カテゴリ補足オプションに関連したレポートフィールドが追加されました。

※2は下位のバージョン（Ver.6.5.0、および6.4.0）にも適用されます。

##### 対象ウェブサービス
 * [FeedItemServcie](/docs/ja/api_reference/services/FeedItemServcie.md)
 * [CampaignFeedService](/docs/ja/api_reference/services/CampaignFeedService.md)
 * [AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

### 3. システムの保守、改善
サイトリターゲティングのターゲットリストがシステム側でクローズされた場合、その理由を取得できるようになるなどの機能改善やシステムの保守を実施しました。<br>
変更内容は「Serviceの変更による各Versionへの影響」の項目をご確認ください。 

##### 対象ウェブサービス 
 * [FeedItemServcie](/docs/ja/api_reference/services/FeedItemServcie.md)
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)
<br>

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
Ver.6.5以前
</th>
<th>
V201805
</th>
</tr>
<tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">
  ・placeholderTypeに以下のenum値が追加されました。<br>
  　‐STRUCTURED_SNIPPET	（カテゴリ補足オプション）<br>
  ・FeedItemPlaceholderFieldに以下のenum値が追加されました。<br>
  　‐STRUCTURED_SNIPPET_HEADER（カテゴリ補足オプション（補足カテゴリー））<br>
  　‐STRUCTURED_SNIPPET_VALUES（カテゴリ補足オプション（補足内容）） <br>
  ・Advanced（AdvancedURL対応フラグ）がselector/operandから削除されました。<br>
  ・DevicePreference（優先デバイス）にNONE（指定なし）が追加されました。
 </td>
</tr>
<tr>
 <td valign="top">CampaignFeedService</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">placeholderTypeに以下のenum値が追加されました。<br>
 　‐STRUCTURED_SNIPPET	（カテゴリ補足オプション）<br></td>
</tr>
<tr>
 <td valign="top">AdGroupFeedService</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">placeholderTypeに以下のenum値が追加されました。<br>
 　‐STRUCTURED_SNIPPET	（カテゴリ補足オプション）<br></td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">インターフェースに変更はありません。<br>
 ※レポートフィールドを追加しました。</td>
 <td valign="top">インターフェースに変更はありません。<br>
 ※レポートフィールドを追加しました。</td>
</tr>
<tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">closingReason（ターゲットリストのクローズ理由）を追加しました。</td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">Advanced（AdvancedURL対応フラグ）がselector/operandから削除されました。</td>
</tr>
<tr>
 <td valign="top">AdGroupCriterionService</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">Advanced（AdvancedURL対応フラグ）がselector/operandから削除されました。</td>
</tr>
<tr>
 <td valign="top">全サービス</td>
 <td valign="top">インターフェースに変更はありません。</td>
 <td valign="top">
     ・バージョン体系の変更<br>
     ・wsdlの構成変更 (Namespaceの細分化)</td>
</tr>
</table>

## スポンサードサーチAPI Ver.6.4の提供終了について
以下の日程でスポンサードサーチAPI Ver.6.4のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2018年6月23日（土）<br>
* システム終了日：2018年7月23日（月）<br>
