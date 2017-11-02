# リリースノート
スポンサードサーチAPI Ver.6.4<br>

## リリースバージョン
6.4 (WSDLバージョン: 6.4.0)

## バージョンアップの種類
マイナーバージョンアップ  

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

#### 1. アドカスタマイザーの改修
アドカスタマイザーで、以下の機能回収を実施しました。

 * データ自動挿入リストのデータ単位（行ごと）での地域ターゲティングに対応しました。
 * アドカスタマイザーのご利用時に、通常広告の作成が不要になりました。挿入用広告とデータ自動挿入リストのセットのみで、アドカスタマイザーを利用できます。
 * IF関数に対応しました。挿入用広告でIF関数を利用すると、デバイス（端末）がスマートフォンの場合、自動的にスマートフォン用の広告文を表示できます。
 * データ自動挿入リストのデータ件数（リスト内のデータ行数）を、1アカウントあたり40万件から100万件に引き上げます。<br>

※APIインターフェイス上の変更は地域ターゲティングのみです。アドカスタマイザーの詳細は、以下のヘルプでご確認ください。<br>
<a href="https://help.marketing.yahoo.co.jp/ja/?cat=627">スポンサードサーチのヘルプ　アドカスタマイザー</a>
<br><br>

##### 対象ウェブサービス  
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
<br><br>

#### 2.	システムの保守、改善
以下のウェブサービスにおいてシステムの保守、改善を実施しました。<br>
変更内容は「Serviceの変更による各Versionへの影響」の項目をご確認ください。
<br>
<br>

##### 対象ウェブサービス
 * [CampaignExportService](/docs/ja/api_reference/services/CampaignExportService.md)
 <br><br>

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
Ver.6.3以前
</th>
<th>
Ver.6.4
</th>
</tr>
<tr>
  <td colspan="3"><b>1.	アドカスタマイザーの改修</b></td>
</tr>
<tr>
 <td valign="top">FeedItemService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">
・データ自動挿入リストのデータ単位（行ごと）での地域ターゲティング（Target Location）に対応しました。<br>
・Locationオブジェクトを新たに追加しました。<br>
・以下のEnumerationを新たに追加しました。<br>
　- FeedItemGeoRestriction<br>
　- CriterionTypeFeedItem<br>
・エラーコードを追加しました。
 </td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">エラーコードを追加しました。
 </td>
</tr>
<tr>
  <td colspan="3"><b>2.	システムの保守、改善の実施</b></td>
</tr>
<tr>
 <td valign="top">CampaignExportService</td>
 <td valign="top">変更ありません。</td>
 <td valign="top">
・getでジョブステータスでの絞込みが可能になりました。また、ジョブIDの指定を必須から任意に変更しました。<br>
・addJobでエクスポートするフィールドの指定が可能になりました。<br>
・getExportFieldsを新規公開しました。これにより、エクスポート可能なフィールドを照会できます。<br>
・以下のオブジェクトを新たに追加しました。<br>
　- CampaignExportFieldAttribute<br>
　- CampaignExportFieldValue<br>
・Advancedオブジェクトを削除しました。<br>
 </td>
</tr>
</table>

## スポンサードサーチAPI 6.2のサポート終了予定日
スポンサードサーチAPI 6.2は、2018年1月24日（水）にサポートを終了する予定です。<br>
<br>
