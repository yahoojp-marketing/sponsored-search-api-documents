# リリースノート
スポンサードサーチAPI V201901

## リリースバージョン
V201901（WSDLバージョン V201901）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. ラベル機能に対応
ラベル機能とは、キャンペーンや広告などの入稿物に目印となる語句を設定し、分類やフィルタリングができる機能です。広告管理ツールでは2018年9月にリリースしました。<br>
機能の詳細は以下のヘルプをご覧ください。<br>
[ラベル機能とは](https://support-marketing.yahoo.co.jp/promotionalads/ss/articledetail?lan=ja&aid=23927)<br>
<br>
スポンサードサーチAPI V201901では主に以下を対応しました。

1. ラベルの新規作成、更新、削除が可能
1. キャンペーンなどへのラベルの設定が可能

##### 対象ウェブサービス
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)
 * [LabelService](/docs/ja/api_reference/services/LabelService.md)
 * [CampaignLabelService](/docs/ja/api_reference/services/CampaignLabelService.md)
 * [AdGroupLabelService](/docs/ja/api_reference/services/AdGroupLabelService.md)
 * [AdGroupAdLabelService](/docs/ja/api_reference/services/AdGroupAdLabelService.md)
 * [AdGroupCriterionLabelService](/docs/ja/api_reference/services/AdGroupCriterionLabelService.md)

### 2. 標準入札設定の追加と「コンバージョン数の最大化」項目の削除
2018年12月に、スポンサードサーチの自動入札の機能として新たに標準入札設定を追加し、入札設定は以下の二通りとなりました。
* 標準入札設定：新たに追加した入札設定です。キャンペーン単位で入札方法を設定します。
* ポートフォリオ入札設定：従来より提供している入札設定です。アカウント単位で入札方法を作成し、複数のキャンペーンに設定可能です。 

変更内容の詳細は以下のお知らせをご覧ください。<br>
[自動入札の機能追加と自動入札タイプの一部提供終了および一部項目の削除について](https://promotionalads.yahoo.co.jp/support/release/594230.html)<br>
<br>
スポンサードサーチAPI V201901では主に以下を対応しました。
1. CampaignServiceにて、以下の自動入札タイプを標準入札設定として設定可能<br>
‐ クリック数の最大化（TARGET_SPEND）<br>
‐ コンバージョン単価の目標値（TARGET_CPA）<br>
‐ 広告費用対効果の目標値（TARGET_ROAS）
1. 自動入札タイプのコンバージョン数の最大化（ENHANCED_CPC）を削除

##### 対象ウェブサービス
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [BiddingStrategyService](/docs/ja/api_reference/services/BiddingStrategyService.md)

### 3. サイトリターゲティングにカスタムキーの設定機能を追加
サイトリターゲティング用タグに、カスタムキーが設定可能になりました。<br>
設定したカスタムキーを利用したターゲットリストを作成することで、より精緻な条件を指定したサイトリターゲティングが行えます。<br>
※2018年12月10日のお知らせでは本機能の名称を「カスタムパラメータ」とお伝えしておりましたが、「カスタムキー」に名称が変更となりました。<br>
<br>
スポンサードサーチAPI V201901では主に以下を対応しました。
1. ターゲットリストの条件にカスタムキーを設定可能
1. カスタムキー設定情報の取得が可能

##### ご注意
V201901のリリース以降、V201808以前のバージョンで、ターゲットリストにカスタムキーの条件を1件以上設定している場合、ターゲットリストの条件取得、更新時の挙動が以下のとおり制限されます。
* ターゲットリストに設定されているすべての条件の取得ができません。
* ターゲットリストの条件更新時、更新前に設定済みの条件はすべて削除され、セットした条件のみが設定されます。

このため、V201808以前のバージョンでカスタムキー（カスタムパラメータ）を利用すると、ユーザーの意図と異なる操作結果となる可能性があります。<br>
V201901のリリース以降は、最新のバージョンをご利用くださいますようお願いいたします。
  
##### 対象ウェブサービス
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

### 4. 広告の品質向上に向けた取り組みへの対応
スポンサードサーチでは、商標権者により商標の使用を制限することでブランドを保護し、広告の品質を高める取り組みを予定しています。<br>
<br>
スポンサードサーチAPI V201901では主に以下を対応しました。
* 商標の使用制限の有無を判別するためのフラグ（TrademarkStatus）と、エラーコードを追加

※商標の使用制限がかけられている場合、入稿時にバリデーションエラーとなります（公開中のすべてのバージョン）。<br>
※本施策の詳細は、後日あらためてお知らせいたします。

##### 対象ウェブサービス
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)

### 5. 自動タグ設定に対応
自動タグ設定とは、セキュリティを強化したブラウザーでもコンバージョン測定が可能なタグの機能です。<br>
<br>
スポンサードサーチAPI V201901では主に以下を対応しました。
* 自動タグの設定情報の参照、更新が可能になります。

※本機能は一部のお客様のみご利用可能です。

##### 対象ウェブサービス
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)

### 6. システムの保守、改善
 * システムの保守、改善として、主に不要な項目の削除、一部WSDLの見直しを実施しました。
 * 2018年9月に[お知らせ](https://biz.marketing.yahoo.co.jp/developercenter/news/574376/)していたとおり、スポンサードサーチAPIの広告グループにおける自動入札設定のレスポンスを修正しました（公開中のすべてのバージョン）。
 * 仕様書のレポートフィールド集に各レポートフィールドの動作を表す「動作区分/Behavior Type」列を追加しました（公開中のすべてのバージョン）。

※「Serviceの変更による各Versionへの影響」の項目もあわせてご確認ください。 

##### 対象ウェブサービス 
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [AdGroupCriterionService](/docs/ja/api_reference/services/AdGroupCriterionService.md)
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [BidLandscapeService](/docs/ja/api_reference/services/BidLandscapeService.md)
 * [AccountTrackingUrlService](/docs/ja/api_reference/services/AccountTrackingUrlService.md)
 * [CampaignTargetService](/docs/ja/api_reference/services/CampaignTargetService.md)
 * [AdGroupWebpageService](/docs/ja/api_reference/services/AdGroupWebpageService.md)
 * [PageFeedItemService](/docs/ja/api_reference/services/PageFeedItemService.md)

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
 <tr>
 <th>Service</th>
 <th>V201808以前</th>
 <th>V201901</th>
 </tr>
 <tr>
 <td valign="top">CampaignService</td>
 <td valign="top">
 ・インターフェース変更なし<br>
 ・設定された以下の自動入札タイプが参照可能<br>
 ‐ 「クリック数の最大化」(TARGET_SPEND)<br>
 ‐ 「コンバージョン単価の目標値」(TARGET_CPA)<br>
 ‐ 「広告費用対効果の目標値」(TARGET_ROAS)<br>
 </td>
 <td valign="top">
 ・ラベルIDの取得が可能<br>
 ・キャンペーン単位の標準入札設定として、以下の自動入札タイプの設定、削除、参照が可能<br>
 ‐ 「クリック数の最大化」(TARGET_SPEND)<br>
 ‐ 「コンバージョン単価の目標値」(TARGET_CPA)<br>
 ‐ 「広告費用対効果の目標値」(TARGET_ROAS)<br>
 ・自動入札タイプ「コンバージョン数の最大化」（ENHANCED_CPC）関連項目の削除<br>
 ・広告表示最適化フラグを削除<br>
 ・旧自動入札機能（2014年7月提供終了）関連項目を削除
 </td>
 </tr>
 <tr>
 <td valign="top">BiddingStrategyService</td>
 <td valign="top">
 インターフェース変更なし
 </td>
 <td valign="top">
 自動入札タイプ「コンバージョン数の最大化」（ENHANCED_CPC）関連項目の削除
 </td>
 </tr>
 <tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">
 ・インターフェース変更なし<br>
 ・商標の使用制限がかけられている場合、入稿時にバリデーションエラーとなる
 </td>
 <td valign="top">
 ・商標の使用制限がかけられている場合、入稿時にバリデーションエラーとなる<br>
 ・商標の使用制限の有無を判別するためのフラグの値を参照可能
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupService</td>
 <td valign="top">
 ・インターフェース変更なし<br>
 ・広告グループにおける自動入札設定のレスポンスを修正<br>
 ※詳細は2018年9月の<a href="https://biz.marketing.yahoo.co.jp/developercenter/news/574376/">お知らせ</a>をご参照ください。
 </td>
 <td valign="top">
 ・ラベルIDの取得が可能<br>
 ・自動入札に関する不要な項目削除<br>
 ・広告グループにおける自動入札設定のレスポンスを修正<br>
 ※詳細は2018年9月の<a href="https://biz.marketing.yahoo.co.jp/developercenter/news/574376/">お知らせ</a>をご参照ください。
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">
 ・インターフェース変更なし <br>
 ・商標の使用制限がかけられている場合、入稿時にバリデーションエラーとなる
 </td>
 <td valign="top">
 ・ラベルIDの取得が可能<br>
 ・商標の使用制限がかけられている場合、入稿時にバリデーションエラーとなる<br>
 ・商標の使用制限の有無を判別するためのフラグの値を参照可能
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupCriterionService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
 ・ラベルIDの取得が可能<br>
 ・自動入札に関する不要な項目削除
 </td>
 </tr>
 <tr>
 <td valign="top">LabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・ラベルの新規作成、更新、削除、参照が可能
 </td>
 </tr>
 <tr>
 <td valign="top">CampaignLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・キャンペーンへのラベルの設定、解除が可能
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・広告グループへのラベルの設定、解除が可能
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupAdLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・広告へのラベルの設定、解除が可能
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupCriterionLabelService</td>
 <td valign="top">-</td>
 <td valign="top">
 ・キーワードへのラベルの設定、解除が可能
 </td>
 </tr>
 <tr>
 <td valign="top">RetargetingListService</td>
 <td valign="top">
 ・インターフェース変更なし <br>
 ・V201808以前のバージョンで、カスタムキー（カスタムパラメータ）の条件を1件以上設定しているターゲットリストにおいて、ターゲットリストの条件取得、更新時の挙動が以下のとおり制限される<br>
 - ターゲットリストに設定されているすべての条件の取得が不可<br>
 - ターゲットリストの条件更新時、更新前に設定済みの条件はすべて削除され、セットした条件のみが設定される
 </td>
 <td valign="top">
 ・ターゲットリストの条件にカスタムキーが設定可能<br>
 ・広告対象のウェブサイトに設定されている、サイトリターゲティング用タグ内のカスタムキーの取得が可能
 </td>
 </tr>
 <tr>
 <td valign="top">BidLandscapeService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
 ・BidLandscapeService.wsdlのselectorにpaging項目を追加
 </td>
 </tr>
 <tr>
 <td valign="top">AccountTrackingUrlService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
 ・AccountTrackingUrlService.wsdlのOperatorのenum値「ADD」を削除（未提供のため）
 </td>
 </tr>
 <tr>
 <td valign="top">ConversionTrackerService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
 ・デバイスをまたいでコンバージョン計測をするかしないかを制御するフラグを削除
 </td>
 </tr>
 <tr>
 <td valign="top">AccountService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
 ・自動タグの設定、参照が可能<br>
 ※本機能は一部のお客様のみご利用可能
 </td>
 </tr>

 <tr>
 <td valign="top">CampaignTargetService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
・CampaignTargetService.wsdlにおいて、Page.TypeとtotalNumEntriesのレスポンスの順番を変更
 </td>
 </tr>
 <tr>
 <td valign="top">AdGroupWebpageService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
 ・AdGroupWebpageService.wsdlにおいて、service nameの誤植を修正
 </td>
 </tr>
 <tr>
 <td valign="top">PageFeedItemService</td>
 <td valign="top">
 ・インターフェース変更なし
 </td>
 <td valign="top">
 ・AdGroupWebpageService.wsdlにおいて、service nameの誤植を修正<br>
 ・AdGroupWebpageService.wsdlにおいて、operationsのmaxOccursを"unbounded"から"1"に修正
 </td>
 </tr>
</tbody>
</table>

## スポンサードサーチAPI V201805の提供終了について
以下の日程でスポンサードサーチAPI V201805のサポート、およびシステムの提供を終了いたします。
* サポート終了日：2019年2月28日（木）<br>
* システム終了日：2019年5月29日（水）<br>
