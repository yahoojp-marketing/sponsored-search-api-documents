# RetargetingListSelector
RetargetingListSelector is an object that holds search condition (parameter) of get method.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>get</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Search conditon: Account ID.</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>targetListIds[0...1000]</td>
  <td>xsd:long</td>
  <td>Search conditon: Target List ID.</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>targetListTypes[0...3]</td>
  <td>enum <a href="./TargetListType.md">TargetListType</a></td>
  <td>Search conditon: Type of Target list type.</td>
  <td>Optional</td>
 </tr>
<tr>
  <td>owner</td>
  <td>enum <a href="./TargetListOwner.md">TargetListOwner</a></td>
  <td>Search conditon: Target list owner information.</td>
  <td>Optional</td>
 </tr>
<tr>
  <td>paging</td>
  <td><a href="./Paging.md">Paging</a></td>
  <td>Search conditon: Page of results.</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
