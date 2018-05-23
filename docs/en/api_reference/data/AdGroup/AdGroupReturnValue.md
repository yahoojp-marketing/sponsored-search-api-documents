# AdGroupReturnValue
AdGroupReturnValue object is a container which has ad group information including its operation results.

### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

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
  <td colspan="8"><a href="../Common/ListReturnValue.md">ListReturnValue</a>(inherited)</td>
 </tr>
 <tr>
  <td>ListReturnValue.Type</td>
  <td>xsd:string</td>
  <td>Indicates the subtype of ListReturnValue of this instance.</td>
  <td colspan="7"></td>
 </tr>
 <tr>
  <td>Operation.Type</td>
  <td>xsd:string</td>
  <td>Details of mutate process.</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">AccountReturnValue</td>
 </tr>
 <tr>
  <td>values[0...2000]</td>
  <td><a href="AdGroupValues.md">AdGroupValues</a></td>
  <td>Details of Ad group and results of mutate process.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
