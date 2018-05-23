# CustomParameters
CustomParameters displays the setting of custom parameters.

### Service
+ [FeedItemService](../../services/FeedItemService.md)

### Namespace
[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

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
  <td>isRemove</td>
  <td>enum <a href="IsRemove.md">IsRemove</a></td>
  <td>Delete flag.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>parameters[0...3]</td>
  <td><a href="CustomParameter.md">CustomParameter</a></td>
  <td>Detail of custom parameter.<br>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>* It will replace the current items.<br>Ignore if delete flag is set (isRemove =TRUE). All item will be deleted.</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
