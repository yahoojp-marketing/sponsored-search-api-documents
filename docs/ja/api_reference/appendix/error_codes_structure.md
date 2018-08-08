# エラーコードの再編について

## 概要
エラーコードの構成上の問題点を改善するために、エラーコードの再編を実施しました。

### 1．エラーコードの構成を見直し
#### 問題点：冗長なエラーコード/メッセージが存在する
* 例：エラーメッセージの内容は同じだが、UpperCase、LowerCaseの違いでエラーコードが異なる。
<table class="standard">
<tbody>
<tr>
<th>エラーコード</th>
<th>エラーメッセージ</th>
</tr>
<tr>
 <td valign="top">0007</td>
 <td valign="top">invalid number format.</td>
</tr>
<tr>
 <td valign="top">20601</td>
 <td valign="top">INVALID_NUMBER_FORMAT</td>
</tr>
</table>

* 例：エラーメッセージの内容は同じだが、CampaignService、AdGroupServiceなど発生するServiceが分かれているためエラーコードが異なる。


<table class="standard">
<tbody>
<tr>
<th>エラーコード</th>
<th>エラーメッセージ</th>
</tr>
<tr>
 <td valign="top">210305</td>
 <td valign="top">Auto bidding is already set.</td>
</tr>
<tr>
 <td valign="top">210404</td>
 <td valign="top">Auto bidding is already set.</td>
</tr>
</table>

#### 対応内容
* 単項目のエラー(必須、形式不正、値不正など)をカテゴリー化しました。
<table class="standard">
<tbody>
<tr>
<th>パターン</th>
<th>カテゴリ</th>
<th>エラーコード</th>
<th>エラーメッセージ</th>
<th>説明</th>
</tr>
<tr>
 <td valign="top" rowspan=2>1</td>
 <td valign="top" rowspan=2>形式不正</td>
 <td valign="top">F0001</td>
 <td valign="top">Invalid format.</td>
 <td valign="top">日付、数値、文字列の形式が不正です。</td>
</tr>
<tr>
 <td valign="top">F0002</td>
 <td valign="top">Invalid file format.</td>
 <td valign="top">アップロードファイルの形式が不正です。</td>
</tr>
<tr>
 <td valign="top">2</td>
 <td valign="top">必須</td>
 <td valign="top">R0001</td>
 <td valign="top">Require.</td>
 <td valign="top">必須項目が未指定です。</td>
</tr>
<tr>
 <td valign="top" rowspan=3>3</td>
 <td valign="top" rowspan=3>値不正</td>
 <td valign="top">V0001</td>
 <td valign="top">Invalid value.</td>
 <td valign="top">文字、日付、数値、ENUMで許可していない値です。</td>
</tr>
<tr>
 <td valign="top">V0002</td>
 <td valign="top">Empty file</td>
 <td valign="top">アップロードファイルサイズが0バイトです。</td>
</tr>
<tr>
 <td valign="top">V0003</td>
 <td valign="top">Over limit of the file</td>
 <td valign="top">アップロードファイルサイズが上限を超過しています。</td>
</tr>
<tr>
 <td valign="top" rowspan=2>4</td>
 <td valign="top" rowspan=2>配列不正</td>
 <td valign="top">L0001</td>
 <td valign="top">Lower list size.</td>
 <td valign="top">配列の要素数が下限値を下回っています。</td>
</tr>
<tr>
 <td valign="top">L0002</td>
 <td valign="top">Over list size.</td>
 <td valign="top">配列の要素数が上限値を超過しています。</td>
</tr>
<tr>
 <td valign="top" rowspan=2>5</td>
 <td valign="top" rowspan=2>URL</td>
 <td valign="top">L0001</td>
 <td valign="top">Url has expired.</td>
 <td valign="top">アップロードURL、またはダウンロードURLの有効期限が切れています。</td>
</tr>
<tr>
 <td valign="top">U0002</td>
 <td valign="top">Invalid url.</td>
 <td valign="top">アップロードURL、またはダウンロードURLが利用できない状態です<br>（URLが改ざんされているなど）。</td>
</tr>
<tr>
 <td valign="top">6</td>
 <td valign="top">ステータス不正</td>
 <td valign="top">S0001</td>
 <td valign="top">Invalid Status.</td>
 <td valign="top">無効なステータスです。変更または削除できません。</td>
</tr>
<tr>
 <td valign="top">7</td>
 <td valign="top">存在しないID</td>
 <td valign="top">I0001</td>
 <td valign="top">Deactivated Id.</td>
 <td valign="top">削除されているEntityのID、または存在しないIDが指定されています。</td>
</tr>
<tr>
 <td valign="top">8</td>
 <td valign="top">重複</td>
 <td valign="top">D0001</td>
 <td valign="top">Duplicate.</td>
 <td valign="top">・Entityを一意に識別する項目が重複しています。<br>
・すでに登録済みの名称と重複しています。<br>
・リクエストで指定したoperand内で名称が重複しています。</td>
</tr>
<tr>
 <td valign="top">9</td>
 <td valign="top">関連不正</td>
 <td valign="top">RL001</td>
 <td valign="top">Invalid relation.</td>
 <td valign="top">リクエストで指定する項目の関連性が矛盾しています<br> （開始＞終了の日付指定を行なっているなど）。</td>
</tr>
<tr>
 <td valign="top">10</td>
 <td valign="top">上限超過</td>
 <td valign="top">LT001</td>
 <td valign="top">Over limit.</td>
 <td valign="top">登録できるEntityの上限数を超過しています。</td>
</tr>
</table>

* エラーメッセージが同一の場合のエラーコードを統合しました。
<table class="standard">
<tbody>
<tr>
<th>エラーコード</th>
<th>エラーメッセージ</th>
<th>削除</th>
<th>統合先エラーコード</th>
</tr>
<tr>
 <td valign="top">210305</td>
 <td valign="top">Auto bidding is already set.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210404</td>
 <td valign="top">Auto bidding is already set.</td>
 <td valign="top">○</td>
 <td valign="top">210305</td>
</tr>
<tr>
 <td valign="top">210405</td>
 <td valign="top">Budget has exceeded.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210507</td>
 <td valign="top">Budget has exceeded.</td>
 <td valign="top">○</td>
 <td valign="top">210405</td>
</tr>
<tr>
 <td valign="top">210306</td>
 <td valign="top">Cannot use conversion optimizer.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210406</td>
 <td valign="top">Cannot use conversion optimizer.</td>
 <td valign="top">○</td>
 <td valign="top">210306</td>
</tr>
<tr>
 <td valign="top">210511</td>
 <td valign="top">Cannot use conversion optimizer.</td>
 <td valign="top">○</td>
 <td valign="top">210306</td>
</tr>
<tr>
 <td valign="top">210400</td>
 <td valign="top">Double setting in Auto bidding.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210500</td>
 <td valign="top">Double setting in Auto bidding.</td>
 <td valign="top">○</td>
 <td valign="top">210400</td>
</tr>
<tr>
 <td valign="top">210303</td>
 <td valign="top">Invalid conversion tracking.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210402</td>
 <td valign="top">Invalid conversion tracking.</td>
 <td valign="top">○</td>
 <td valign="top">210303</td>
</tr>
<tr>
 <td valign="top">210502</td>
 <td valign="top">Invalid conversion tracking.</td>
 <td valign="top">○</td>
 <td valign="top">210303</td>
</tr>
<tr>
 <td valign="top">210304</td>
 <td valign="top">Not enough conversions or invalid setting.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210403</td>
 <td valign="top">Not enough conversions or invalid setting.</td>
 <td valign="top">○</td>
 <td valign="top">210304</td>
</tr>
<tr>
 <td valign="top">210503</td>
 <td valign="top">Not enough conversions or invalid setting.</td>
 <td valign="top">○</td>
 <td valign="top">210304</td>
</tr>
<tr>
 <td valign="top">210308</td>
 <td valign="top">Set campaign active.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210407</td>
 <td valign="top">Set campaign active.</td>
 <td valign="top">○</td>
 <td valign="top">210308</td>
</tr>
<tr>
 <td valign="top">210512</td>
 <td valign="top">Set campaign active.</td>
 <td valign="top">○</td>
 <td valign="top">210308</td>
</tr>
<tr>
 <td valign="top">210309</td>
 <td valign="top">Set campaign to Manual CPC.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210408</td>
 <td valign="top">Set campaign to Manual CPC.</td>
 <td valign="top">○</td>
 <td valign="top">210309</td>
</tr>
<tr>
 <td valign="top">210513</td>
 <td valign="top">Set campaign to Manual CPC.</td>
 <td valign="top">○</td>
 <td valign="top">210309</td>
</tr>
<tr>
 <td valign="top">210301</td>
 <td valign="top">Setting the disabled Auto bidding.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">210401</td>
 <td valign="top">Setting the disabled Auto bidding.</td>
 <td valign="top">○</td>
 <td valign="top">210301</td>
</tr>
<tr>
 <td valign="top">210501</td>
 <td valign="top">Setting the disabled Auto bidding.</td>
 <td valign="top">○</td>
 <td valign="top">210301</td>
</tr>
<tr>
 <td valign="top">1000</td>
 <td valign="top">creating downloadUrl is failed.</td>
 <td valign="top">○</td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">2000</td>
 <td valign="top">creating bulk downloadUrl is failed.</td>
 <td valign="top">○</td>
 <td valign="top"></td>
</tr>
</table>

### 2．無効なエラーコードを削除
現在使用していない以下のエラーコードを削除しました。
<table class="standard">
<tbody>
<tr>
<th>エラーコード</th>
<th>エラーメッセージ</th>
</tr>
<tr>
 <td valign="top">210103</td>
 <td valign="top">UNMATCH PLACEHOLDER TYPE</td>
</tr>
<tr>
 <td valign="top">210506</td>
 <td valign="top">Invalid keyword settings.</td>
</tr>
<tr>
 <td valign="top">240007</td>
 <td valign="top">Is Not Template.</td>
</tr>
</table>

## エラーコード統廃合の状況一覧
エラーコードの統廃合状況一覧は以下のファイルをダウンロードしてご確認ください。<br>
[エラーコード統廃合（スポンサードサーチAPI）](https://s.yimg.jp/images/promotionalads_edit/support/pdf/api_doc/error_codes_structure_SS_ja.pdf)

