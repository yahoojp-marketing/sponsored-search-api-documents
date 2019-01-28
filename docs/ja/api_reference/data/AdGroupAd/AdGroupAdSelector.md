# AdGroupAdSelector
AdGroupAdSelectorオブジェクトは、操作の対象とする広告およびフィルタ条件を表します。

### Service
+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace
[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>検索条件：アカウントID</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignIds[0...1000]</td>
  <td>xsd:long</td>
  <td>検索条件：キャンペーンID</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupIds[0...1000]</td>
  <td>xsd:long</td>
  <td>検索条件：広告グループID</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adIds[0...1000]</td>
  <td>xsd:long</td>
  <td>検索条件：広告ID</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adTypes[0...4]</td>
  <td>enum <a href="AdType.md">AdType</a></td>
  <td>検索条件：広告の種類</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>userStatuses[0...2]</td>
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>検索条件：ユーザーにより設定される広告の掲載状況<br>※指定しない 場合は、フィルタ条件にすべての掲載状況が含まれます。</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>approvalStatuses[0...5]</td>
  <td>enum <a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>検索条件：審査状況</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>labelIds[0...1000]</td>
  <td>xsd:long</td>
  <td>検索条件：ラベルID</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>containsLabelId</td>
  <td>enum <a href="ContainsLabelId.md">ContainsLabelId</a></td>
  <td>検索条件：ラベル情報取得フラグ</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>検索条件：取得範囲</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
