# DefaultTargetList
DefaultTargetList is an object that holds default target list.

### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

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
  <td colspan="8"><a href="TargetingList.md">TargetingList</a>(inherited)</td>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>retargetingAccountStatus</td>
  <td><a href="RetargetingAccountStatus.md">RetargetingAccountStatus</a></td>
  <td>Retargeting account status.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetListId</td>
  <td>xsd:long</a></td>
  <td>Target list ID. </td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>targetListType</td>
  <td>enum <a href="TargetListType.md">TargetListType</a></td>
  <td>Target list type.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
  <tr>
  <td>targetListName</td>
  <td>xsd:string</a></td>
  <td>Target list name. </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
  <tr>
  <td>targetListDescription</td>
  <td>xsd:string</a></td>
  <td>Description of target list.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reachStorageStatus</td>
  <td>enum <a href="ReachStorageStatus.md">ReachStorageStatus</a></td>
  <td>Flag status to hold Cookie.<br>*Default: OPEN</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Ignore for Logical TargetList.</td>
  <td>Optional<br>*Ignore for Logical TargetList.</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reachStorageSpan</td>
  <td>xsd:long</a></td>
  <td>Days to hold Cookie.<br>*Default: 180</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Ignore for Logical TargetList.</td>
  <td>Optional<br>*Ignore for Logical TargetList.</td>
  <td>-</td>
 </tr>
  <tr>
  <td>reach</td>
  <td>xsd:long</a></td>
  <td>Number of users stored to the list.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td></td>
  <td>-</td>
 </tr>
  <tr>
  <td>targetListTrackId</td>
  <td>xsd:long</a></td>
  <td>Tracking ID of Target List.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">DefaultTargetList</td>
 </tr>
  <tr>
  <td>tag</td>
  <td><a href="Tag.md">Tag</a></a></td>
  <td>Object that holds tag of retargeting.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
