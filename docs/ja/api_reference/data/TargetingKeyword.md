# TargetingKeyword
TargetingKeywordオブジェクトは、データ自動挿入のターゲットキーワードを表します。

### Service
+ [FeedItemService](../services/FeedItemService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>targetingKeywordId</td>
  <td>xsd:long</td>
  <td>指定したキーワード（text）を識別する IDになります。<br>※設定を解除する場合は「0」を指定 してください。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>text</td>
  <td>xsd:string</td>
  <td>指定するキーワードです。<br>※入力制限：80文字、10ワード までです。 </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>matchType</td>
  <td>enum <a href="./KeywordMatchType.md">KeywordMatchType</a></td>
  <td>マッチタイプです。<br>入力されたキーワードが検索クエリに どのように一致するかを示します。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
