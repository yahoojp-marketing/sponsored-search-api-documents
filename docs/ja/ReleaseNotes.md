# リリースノート
スポンサードサーチAPI Ver.6.5<br>

## リリースバージョン
6.5 (WSDLバージョン: 6.5.0)

## バージョンアップの種類
マイナーバージョンアップ  

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

#### 1. デバイスをまたいだコンバージョン測定に対応（ウェブサイトと電話発信）
従来のCookie情報に加えて、ログイン情報も用いたコンバージョン測定に対応しました。<br>
これにより、パソコンで広告をクリックした後にスマートフォンで購入するといった、デバイス（端末）をまたいだコンバージョンの測定が可能になりました。<br>
主な機能の変更点は以下のとおりです。
1. デバイスをまたいでコンバージョンを測定するか、しないかを制御するフラグを追加しました。
1. コンバージョン測定用のレポートフィールドを追加しました。

##### 対象ウェブサービス  
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
<br><br>

#### 2. 広告表示の最適化設定を広告グループ単位に変更
広告表示の最適化について、従来のキャンペーン単位から、広告グループ単位への設定に変更しました。
<br>
主な機能の変更点は以下のとおりです。
1. 広告グループに「広告表示の最適化」の項目を追加しました。<br>「広告表示の最適化」項目で設定できる値は以下の2つです。
    - OPTIMIZE：最適化して広告を配信する
    - ROTATE_FOREVER：広告は常に均等に配信される（最適化しない）
1. キャンペーンの「広告表示の最適化」項目は読み取り専用になりました。<br>
    - キャンペーンを作成した場合、「広告表示の最適化」項目は、一律「OPTIMIZE」が設定されます。<br>このため「OPTIMIZE」以外の値を指定した場合でも「OPTIMIZE」に値が置き換えられてキャンペーンが作成されます。
    - キャンペーンを更新した場合、「広告表示の最適化」項目は、設定済みの値がレスポンスされます。任意の値には変更できません。
1. キャンペーンのadServingOptimizationStatus（広告表示の最適化）項目で以下の値が設定されている場合、広告配信時は「OPTIMIZE（最適化して広告を配信する）」が適用されるようになりました。
    - ROTATE
    - CONVERSION_OPTIMIZE

※2、3は下位のバージョン（Ver.6.4.0、および6.3.0）にも適用されます。

##### 対象ウェブサービス  
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
<br><br>

#### 3. アプリコンバージョン測定の設定を変更
アプリダウンロードキャンペーンのコンバージョン測定において、同一パッケージで「ダウンロード」と「初回起動」の両方を「自動入札に利用する」設定は不可となりました。
<br>
主な機能の変更点は以下のとおりです。
1. 以下の2つの操作を行った場合にエラーとなるように、バリデーションを追加しました。
    - 同一のappId（アプリケーションID）に対して、以下の2つの設定を同時に行った場合<br>
    アプリコンバージョン種別「ダウンロード」/「自動入札に利用する」<br>
    アプリコンバージョン種別「初回起動」/「自動入札に利用する」
    - 同一のappIdに対して、事前にアプリコンバージョン種別「ダウンロード」、かつ「自動入札に利用しない」の組み合わせのコンバージョン設定がない状態で、「初回起動」、かつ「自動入札に利用する」のコンバージョンを設定しようとした場合
1. アプリのコンバージョン設定をappId（アプリケーションID）で検索できるようになりました。

※1は下位のバージョン（Ver.6.4.0、および6.3.0）にも適用されます。

##### 対象ウェブサービス  
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
<br><br>

## Serviceの変更による各Versionへの影響
<table class="standard">
 <tbody>
<tr>
<th>
Service
</th>
<th>
Ver.6.4以前
</th>
<th>
Ver.6.5
</th>
</tr>
<tr>
 <td valign="top">ConversionTrackerService</td>
 <td valign="top">インターフェースに変更はありません。<br>※エラーコードを追加しました。</td>
 <td valign="top">
  ・デバイスまたぎでコンバージョンを測定するか、しないかを制御するフラグ（CrossDeviceConversionFlag）を追加しました。<br>
  ・アプリのコンバージョン設定がアプリケーションID（appId）で検索可能になりました。<br>
  ・エラーコードを追加しました。
  </td>
</tr>
<tr>
 <td valign="top">ReportDefinitionService</td>
 <td valign="top">インターフェースに変更はありません。<br>※レポートフィールドを追加しました。</td>
 <td valign="top">インターフェースに変更はありません。<br>※レポートフィールドを追加しました。</td>
</tr>
<tr>
 <td valign="top">CampaignService</td>
 <td valign="top">
  ・キャンペーンでの広告表示の最適化（adServingOptimizationStatus）は読み取り専用の項目になりました。<br>
  ・ADD、SETのリクエストではadServingOptimizationStatusはIgnoreになります。<br>
  ・ADD、SETのレスポンスでは、ADDの場合は「OPTIMIZE」が、SETの場合は既に設定済みの値がadServingOptimizationStatusにレスポンスされます。
 </td>
 <td valign="top">
  ・キャンペーンでの広告表示の最適化（adServingOptimizationStatus）は読み取り専用の項目になりました。<br>
  ・ADD、SETのリクエストでは、adServingOptimizationStatus項目はIgnoreになります。<br>
  ・ADD、SETのレスポンスでは、ADDの場合は「OPTIMIZE」が、SETの場合は既に設定済みの値がadServingOptimizationStatusにレスポンスされます。
  </td>
</tr>
<tr>
 <td valign="top">AdGroupService</td>
 <td valign="top">インターフェースに変更はありません。<br>※広告表示の最適化項目の設定（追加/更新/参照）はできません。</td>
 <td valign="top">
  ・広告表示の最適化項目（AdGroupAdRotationMode）を追加しました。<br>
  ・広告グループで広告表示の最適化の設定（追加/更新/参照）ができます。</td>
</tr>
<tr>
 <td valign="top">CampaignRetargetingListService</td>
 <td valign="top">インターフェースに変更はありません。<br>※エラーコードを追加しました。</td>
 <td valign="top">インターフェースに変更はありません。<br>※エラーコードを追加しました。</td>
</tr>
<tr>
 <td valign="top">AdGroupRetargetingListService</td>
 <td valign="top">インターフェースに変更はありません。<br>※エラーコードを追加しました。</td>
 <td valign="top">インターフェースに変更はありません。<br>※エラーコードを追加しました。</td>
</tr>
</table>

## スポンサードサーチAPI 6.3のサポート終了予定日
スポンサードサーチAPI 6.3は、2018年3月末頃にサポートを終了する予定です。<br>
<br>
