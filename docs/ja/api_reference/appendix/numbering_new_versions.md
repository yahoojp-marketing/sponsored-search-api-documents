# バージョン体系とwsdl構成の変更について

## バージョン体系の変更
システムリリースのスケジュールを定期化したことに伴い、バージョン体系を変更いたしました。
* 変更前<br>
VX.X （例：V6.5）
* 変更後<br>
VYYYYMM （例：V201805）

## wsdl構成の変更（NameSpaceの細分化）
一部の環境において、自動生成によりEntityが重複してしまう問題を解消するため、NameSpaceを細分化しオブジェクトの構成を変更いたしました。

* 変更前<br>
http://ss.yahooapis.jp/V6
* 変更後<br>
http://ss.yahooapis.jp/V201805<br>
http://ss.yahooapis.jp/V201805/Service名<br>（例：Account、Campaign、AdGroup）

### 変更後のNameSpaceに属する要素
#### Service横断で利用する要素
Soapリクエスト・レスポンスにおいて、各サービスで共通的に使用するエンティティは以下のNameSpaceに集約します。
<table class="standard">
<tbody>
<tr>
<th>
NameSpace
</th>
<th>
要素（Entity）
</th>
<th>
説明
</th>
</tr>
<tr>
 <td valign="top" rowspan=8>http://ss.yahooapis.jp/V201805</td>
 <td valign="top">SoapHeader<br>
 ・license<br>
 ・apiAccountId<br>
 ・apiAccountPassword<br>
 ・accountId<br>
 ・onBehalfOfAccountId<br>
 ・onBehalfOfPassword
 </td>
 <td valign="top">Soapヘッダー（認証情報）<br>
 ・ライセンス<br>
 ・APIアカウントID<br>
 ・APIアカウントパスワード<br>
 ・アカウントID<br>
 ・代行アカウントID<br>
 ・代行アカウントパスワード<br>
 </td>
</tr>
<tr>
 <td valign="top">SoapResponseHeader<br>
 ・service<br>
 ・timeTakenSeconds<br>
 ・requestTime
 </td>
 <td valign="top">Soapレスポンスヘッダー<br>
 ・サービス名<br>
 ・処理時間<br>
 ・処理受付時間（Unixタイムスタンプ）<br>
 </td>
</tr>
<tr>
 <td valign="top">Paging<br>
 ・startIndex<br>
 ・numberResults
 </td>
 <td valign="top">ページング<br>
 ・取得開始Index<br>
 ・取得最大件数
 </td>
</tr>
<tr>
 <td valign="top">Error<br>
 ・code<br>
 ・message<br>
 ・detail
 </td>
 <td valign="top">エラー情報<br>
 ・エラーコード<br>
 ・エラーメッセージ<br>
 ・エラー詳細情報
 </td>
</tr>
<tr>
 <td valign="top">ErrorDetail<br>
 ・requestKey<br>
 ・requestValue
 </td>
 <td valign="top">エラー詳細情報<br>
 ・エラー項目<br>
 ・エラー値
 </td>
</tr>
<tr>
 <td valign="top">Page<br>
 ・totalNumEntries<br>
 ・Page.Type</td>
 <td valign="top">getメソッドの実行結果情報<br>
 ・取得全件数（ページごとではなく全件）<br>
 ・サービス名＋'Page'
 </td>
</tr>
<tr>
 <td valign="top">ReturnValue<br>
 ・operationSucceeded<br>
 ・error
 </td>
 <td valign="top">get/mutateメソッドの実行結果情報<br>
 ・処理が成功したかどうか<br>
 ・エラー情報</td>
</tr>
<tr>
 <td valign="top">ListReturnValue<br>
 ・ListReturnValue.Type<br>
 ・Operation.Type</td>
 <td valign="top">mutateメソッドの実行結果情報<br>
 ・サービス名＋'ReturnValue'<br>
 ・'ADD' or 'SET' or 'REMOVE'
 </td>
</tr>
</table>

#### Service固有の要素
Soapリクエスト・レスポンスにおいて、各サービスでのみ使用するエンティティ・Enumは以下のように、各サービスのNameSpaceに集約します。
</table>
<table class="standard">
<tbody>
<tr>
<th>
NameSpace
</th>
<th>
要素（Entity、Enum）
</th>
</tr>
<tr>
 <td valign="top">http://ss.yahooapis.jp/V201805/Service名</td>
 <td valign="top">サービス固有の要素<br>
 （例： 〜Selector、〜Operation、Ad、AdGroup、Campaign、AdType）</td>
 </td>
</tr>
