# リリースノート
スポンサードサーチAPI ver.5.2
## リリースバージョン
5.2 (WSDLバージョン: 5.2.0)
## バージョンアップの種類
マイナーバージョンアップ  
※バージョンアップの種類についてはこちらをご確認ください。
## 本リリースの主な内容

#### 1. データ自動挿入機能の追加
商品名や商品価格などのデータを広告に挿入する機能を追加しました。  
また、現在時点から終了日までの残りの日時を広告に挿入するカウントダウン機能を追加しました。  
##### 入稿としては、以下のように設定できます。
* データ挿入機能  

> タイトル：**{=掃除機.モデル}** 販売  
> 表示URL：www.example.com  
> 説明文1	：**{=掃除機.開始価格}** からご用意！  
> 説明文2	：日本全国どこでも配送料無料  

* カウントダウン機能  

> タイトル：掃除機セール中  
> 表示URL：www.example.com  
> 説明文1	：半年に一回のチャンス！  
> 説明文2	：セール終了まであと**{=COUNTDOWN(掃除機.セール終了日,”ja”,5)}**  

※第1引数には、リスト名を指定し、第3引数には、セール終了日の何日前からカウントダウンを開始するか（例では5日）を指定。

##### 下の設定例の1行目のデータを反映された場合、入稿されたデータ挿入とカウントダウンは以下のように配信されます。  

* データ挿入機能とカウントダウン機能の設定例
<table class="standard">
<tbody><tr>
    <th rowspan="2" valign="top">
        <p>リスト名</p>
    </th>
    <th colspan="3" valign="top">
        <p>カラム名</p>
    </th>
    <th rowspan="2" valign="top">
        <p>配信キャンペーン</p>
    </th>
    <th rowspan="2" valign="top">
        <p>配信広告グループ</p>
    </th>
</tr>
<tr>
    <th valign="top">
        <p>モデル</p>
    </th>
    <th valign="top">
        <p>開始価値</p>
    </th>
    <th valign="top">
        <p>セールス終了日</p>
    </th>
</tr>
<tr>
    <td rowspan="3" valign="middle">
        <p></p><center>掃除機</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>ルンバ630</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>32,000円</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>2015/01/15</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>掃除機_海外</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>ロボット掃除機</center><p></p>
    </td>
</tr>
<tr>
    <td valign="top">
        <p></p><center>ダイソンDC61</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>29,000円</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>2015/01/20</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>掃除機_海外</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>ハンディ掃除機</center><p></p>
    </td>
</tr>
<tr>
    <td valign="top">
        <p></p><center>トルネオVC-RV1</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>59,800円</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>2015/02/23</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>掃除機_国内</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>ロボット掃除機</center><p></p>
    </td>
</tr>
</tbody></table>

* データ挿入機能

> **ルンバ630** 販売  
> www.example.com  
> **32,000円** からご用意！日本全国どこでも配送料無料  

* カウントダウン機能

（2015/01/13に以下の広告が表示された場合）  

> 掃除機セール中  
> www.example.com  
> 半年に一回のチャンス！セール終了まであと**2日**  
  
##### 配信キャンペーン、配信広告グループなどのターゲッティングエンティティの指定はパターンによって変わり、対応表は以下の通りです。

<table class="standard">
<tbody><tr>
    <th valign="top">
        <p>パターン</p>
    </th>
    <th valign="top">
        <p>配信キャンペーン</p>
    </th>
    <th valign="top">
        <p>配信広告グループ</p>
    </th>
    <th valign="top">
        <p>配信キーワード</p>
    </th>
    <th valign="top">
        <p>マッチタイプ</p>
    </th>
</tr>
<tr>
    <td valign="top">
        <p>特定のキャンペーン</p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p> </p>
    </td>
    <td valign="top">
        <p> </p>
    </td>
    <td valign="top">
        <p> </p>
    </td>
</tr>
<tr>
    <td valign="top">
        <p>特定の広告グループ</p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p> </p>
    </td>
    <td valign="top">
        <p> </p>
    </td>
</tr>
<tr>
    <td valign="top">
        <p>特定のキャンペーン配下の特定のキーワード</p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p> </p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
</tr>
<tr>
    <td valign="top">
        <p>特定の広告グループ配下の特定のキーワード</p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
    <td valign="top">
        <p></p><center>○</center><p></p>
    </td>
</tr>
</tbody>
</table>

※各データの挿入対象とするエンティティは自由に指定が可能です。<br>
※本件で出てきたエンティティは、以下を表しております。<br>
・リスト名：feedFolder<br>
・カラム名：feedAttribute<br>
・配信キャンペーン：targetCampaign<br>
・配信広告グループ：targetAdGroup<br>

* 対象ウェブサービス  
 * [AdGroupFeedService](/docs/ja/api_reference/services/AdGroupFeedService.md)
 * [FeedItemService](/docs/ja/api_reference/services/FeedItemService.md)
 * [FeedFolderService](/docs/ja/api_reference/services/FeedFolderService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
  
* 対象データオブジェクト  
 * データオブジェクト集をご確認ください。
  
* 対象Enumerations  
 * Enumeration集をご確認ください。
  
#### 2. 広告グループの機能追加
広告グループを横断で入稿できるようになりました。  
広告およびフィルタ条件のオブジェクトに広告種別を追加しております。  
また、1リクエストあたりの入稿上限を引き上げました。  
  
* 対象ウェブサービス
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
  
* 対象データオブジェクト  
 * データオブジェクト集をご確認ください。
  
* 対象Enumerations  
 * Enumeration集をご確認ください。

#### 3. Serviceの変更による各Versionへの影響

<table class="standard">
 <tbody>
<tr>
<th valign="top">
  <p>Service</p>
</th>
<th valign="top">
  <p>Ver.5.1以前</p>
</th>
<th valign="top">
  <p>Ver.5.2</p>
</th>
 </tr>
 <tr>
<td valign="top">
  <p>AdGroupAdService</p>
</td>
<td valign="top">
  <p>- APIIF変更なし<br>
・広告グループを横断した入稿はできません。</p>
</td>
<td valign="top">
  <p>- APIIF変更あり<br>
・AdGroupAdSelector（getの検索条件）でadTypesを追加し、1リクエストの上限数が増加しました。<br>
・AdGroupAdでfeedFolderId（FeedフォルダーID）を追加しました。<br>
・Ad（クリエイティブ情報）にdisplayUrl（表示URL）を追加しました。<br>
<br>
■Error<br>
・存在しないFeedが指定された場合には、「210122：Non existing feed has been set.」を返します。<br>
・1つの広告内に複数のFeedが含まれて場合には、「210601：Multiple feeds are set in one ad.」を返します。<br>
・文字列の指定の仕方が不正の場合には、「210602：Insertion is over the limit.」を返します。<br>
　※Ver.5.1に存在している「20701：INVALID_STRING_　FORMAT」からエラーコードと文言が変更になります。</p>
</td>
 </tr>
 <tr>
<td valign="top">
  <p>FeedItemService</p>
</td>
<td valign="top">
  <p>-APIIF変更なし<br>
・データ挿入機能とカウントダウン機能の入稿はできません。</p>
</td>
<td valign="top">
  <p>- APIIF変更あり<br>
・targetingCampaign、targeting AdGroup、targetingKeyword（データ挿入機能とカウントダウン機能の設定）を追加しました。<br>
　これらの利用で、配信先との紐付け設定が可能です。<br>
<br>
■Error<br>
・存在しないFeedが指定された場合には、「210122：Non existing feed has been set.」を返します。</p>
</td>
 </tr>
 <tr>
<td valign="top">
  <p>FeedFolderService</p>
</td>
<td valign="top">
  <p>- 提供なし</p>
</td>
<td valign="top">
  <p>- 新規公開<br>
・本Serviceで、FeedFolder（データ挿入機能やカウントダウン機能で必要なリスト名）とFeedAttribute（データ挿入機能やカウントダウン機能で必要なカラム名）を操作できます。<br>
<br>
■Error<br>
・存在しないFeedが指定された場合には、「210122：Non existing feed has been set.」を返します。</p>
</td>
 </tr>
 <tr>
<td valign="top">
  <p>ReportDefinitionService</p>
</td>
<td valign="top">
  <p>- APIIF変更なし</p>
</td>
<td valign="top">
  <p>- APIIF変更あり<br>
・ReportDefinition（レポート定義情報）にfeedFolderIdsを追加しました。<br>
　こちらの利用で、データ挿入機能のパフォーマンスレポート作成が可能です。
</p>
</td>
 </tr>
</tbody>
</table>

## 技術ドキュメント
本リリースの内容が含まれたドキュメントは、スポンサードサーチ Ver.5.2です。

## 公開環境
2013年12月16日時点では、サンドボックス環境のみご利用頂けます。<br>
なお、プロダクション環境のリリースは2014年1月30日（木）を予定しています。


## SS API Ver.5.1のご利用について
スポンサードサーチAPI Ver.5.1も引き続きご利用いただけます

## スポンサードサーチAPI Ver.5.0のサポート終了予定日
スポンサードサーチAPI Ver.5.0は、2015年9月以降にサポート終了予定です。
※決定次第、あらためてお知らせいたします。 
