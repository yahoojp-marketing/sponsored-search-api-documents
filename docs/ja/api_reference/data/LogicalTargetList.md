# LogicalTargetList
LogicalTargetListは、組合せターゲットリストの情報を保持するオブジェクトです。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

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
  <td colspan="8"><a href="./TargetingList.md">TargetingList</a>(inherited)</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>retargetingAccountStatus</td>
  <td><a href="./RetargetingAccountStatus.md">RetargetingAccountStatus</a></td>
  <td>アカウントのリタゲ審査ステータスです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetListId</td>
  <td>xsd:long</a></td>
  <td>ターゲットリストIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetListType</td>
  <td>enum <a href="./TargetListType.md">TargetListType</a></td>
  <td>ターゲットリスト種別です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
  <tr>
  <td>targetListName</td>
  <td>xsd:string</a></td>
  <td>ターゲットリスト名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
  <tr>
  <td>targetListDescription</td>
  <td>xsd:string</a></td>
  <td>ターゲットリストの説明です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reachStorageStatus</td>
  <td>enum <a href="./ReachStorageStatus.md">ReachStorageStatus</a></td>
  <td>Cookieの保持かのステータスです。<br>※Default：OPEN</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※Logical TargetListの場合、Ignore</td>
  <td>Optional<br>※Logical TargetListの場合、Ignore</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reachStorageSpan</td>
  <td>xsd:long</a></td>
  <td>Cookieを保持する日数です。<br>※Default：180</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※Logical TargetListの場合、Ignore</td>
  <td>Optional<br>※Logical TargetListの場合、Ignore</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reach</td>
  <td>xsd:long</a></td>
  <td>リストに蓄積されているユーザー数です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetListTrackId</td>
  <td>xsd:long</a></td>
  <td>ターゲットリストのトラッキングIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">LogicalTargetList</td>
 </tr>
 <tr>
  <td>logicalGroup[1...20]</td>
  <td><a href="./LogicalGroup.md">LogicalGroup</a></a></td>
  <td>組み合わせグループです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
