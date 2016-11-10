# リリースノート
スポンサードサーチAPI Ver.6.2<br>

## リリースバージョン
6.2 (WSDLバージョン: 6.2.0)

## バージョンアップの種類
マイナーバージョンアップ  

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

#### 1. 拡大テキスト広告の対応
テキスト広告のタイトルを2行、説明文を1行で設定できる「拡大テキスト広告」に対応します。従来より情報量や広告の表示幅を増やした形式での広告配信が可能です。<br><br>

##### 対象ウェブサービス  
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
<br><br>

#### 2.	デバイスごとの入札調整率の改善
入札価格調整率を、PC、タブレット、スマートフォンの各デバイスごとに設定できます。キャンペーンまたは広告グループ単位での設定が可能です。<br>
<br>

##### 対象ウェブサービス
 * [CampaignTargetService](/docs/ja/api_reference/services/CampaignTargetService.md)
 * [AdGroupBidMultiplierService](/docs/ja/api_reference/services/AdGroupBidMultiplierService.md)
<br><br>

#### 3.	コンバージョン計測方法の機能変更
コンバージョンの計測で、以下の各項目を変更します。
 * 測定方法で「ユニーク」か「合計」のいずれかを指定したコンバージョンタグの発行
 * 自動入札を対象外とするコンバージョンタグの発行
 * コンバージョン計測期間の変更(現在の30日間固定から、7～90日間で指定可能に)
 * コンバージョン実績値（レスポンス）の項目を変更します。
<br><br>

##### 対象ウェブサービス
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
<br><br>

#### 4.	サイトリターゲティング複数設定に伴う変更
2016年10月19日に開始した広告グループへのサイトリターゲティングの複数設定（Ver6.0、6.1で対応済み）に伴い、「TargetAll」オブジェクトを削除します。

##### 対象ウェブサービス
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
<br><br>


#### 5.	保守改善の追加
* レポート定義の作成時に、以下の条件が指定可能になります。<br>
 - レポートの出力対象にインプレッションが0のデータを含める<br>
 - レポート出力対象に削除済みエンティティを含める<br>
 
* デバイスターゲティングレポートを廃止します。
<br>
<br>

##### 対象ウェブサービス
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
<br><br>


## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.6.1以前</p>
</th>
<th valign="top">
  <p>Ver.6.2</p>
</th>
</tr>
<tr>
  <td colspan="3"><b>拡大テキスト広告の対応</b></td>
</tr>
<tr>
 <td valign="top">AdGroupAdService</td><td valign="top">変更ありません</td><td valign="top">
・拡大テキスト広告を登録、照会できる<br>
・一部オブジェクトの変更<br>　-ExtendedTextAdを追加<br>　-MobileAdを削除
</td>
</tr>
<tr>
  <td colspan="3"><b>デバイスごとの入札調整率の改善</b></td>
</tr>
<tr>
 <td valign="top">CampaignTargetService</td><td valign="top">入札価格調整率は、スマートフォンのみ設定可能（キャンペーン単位）</td><td valign="top">
PC、タブレット、スマートフォンのそれぞれに、入札価格調整率を設定、照会できる（キャンペーン単位）</td>
</tr>
<tr>
 <td valign="top">AdGroupBidMultiplierService</td><td valign="top">入札価格調整率は、スマートフォンのみ設定可能（広告グループ単位）</td><td valign="top">
・PC、タブレット、スマートフォンのそれぞれに、入札価格調整率を設定、照会できる（広告グループ単位）<br>
・エラーコードの追加<br>
キャンペーンでデバイス別入札価格調整率を0（そのデバイスには配信しない）で設定中に、広告グループで同デバイスの入札価格調整率を変更しようとした場合、以下のエラーコードを表示<br>
「211006：Cannot bid modify criterion campaign opted out」<br>
・以下のオブジェクトの削除<br>
　-BidMultiplierList<br>
　-PlatformBidMultiplierList<br>
　-PlatformBidMultiplier<br>
　-BidMultiplierType<br>
</td>
</tr>

<tr>
  <td colspan="3"><b>コンバージョン計測方法の項目追加</b></td>
</tr>
<tr>
 <td valign="top">ConversionTrackerService</td><td valign="top">・countingTypeの設定、照会はできない<br>・自動入札に含めるかの選択が<br>できない<br>・コンバージョン計測期間は30日間<br>固定
</td><td valign="top">・countingTypeの設定、照会ができる<br>・自動入札に含めるか、含めないかを選択できる<br>・コンバージョン計測期間を7～90日間で設定できる<br>※アプリダウンロードキャンペーンのみ30日間固定<br>
・コンバージョン実績値（レスポンス）で、以下の項目を変更<br>
　-totalAllConversionsを新設<br>
　-totalAllConversionValueを新設<br>
　-allConversionsを新設<br>
　-allConversionValueを新設<br>
　-numConversionEventsをconversionsに変更<br>
　-totalNumConversionEventsを<br>totalConversionsに変更<br>
　-totalNumConvertedClicksを廃止<br>
　-numConvertedClicksを廃止<br>
・一部オブジェクトの変更<br>
　-ConversionCountingTypeを追加<br>
　-ExcludeFromBiddingを追加<br>
　-HttpProtocolを削除
</td>
</tr>
<tr>
  <td colspan="3"><b>サイトリターゲティング複数設定に伴う変更</b></td>
</tr>
<tr>
 <td valign="top">AdGroupService</td>
 <td valign="top">・2016年10月19日以降、広告グループにサイトリターゲティングの複数設定が可能<br>・2016年10月19日以降、TargetAllの設定が無効</td>
 <td valign="top">・広告グループにサイトリターゲティングの複数設定が可能<br>・TargetAllを削除
</td>
</tr>
<tr>
  <td colspan="3"><b>保守改善の追加</b></td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td><td valign="top">・0インプレッションを含めるかの設定は、filtersでのみ可能<br>・レポートの出力対象に、削除済みエンティティの有無を設定できない
</td><td valign="top">・レポート定義設定時に、0インプレッションを含めるかを設定できる<br>・レポートの出力対象に、削除済みエンティティを含めるかを設定できる<br>・デバイスターゲティングレポートを廃止
</td>
</tr>
</table>
