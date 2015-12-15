# TargetingAdGroup
TargetingAdGroupオブジェクトは、データ自動挿入の広告グループとの紐付けを表します。

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
  <td>targetingAdGroupId</td>
  <td>xsd:long</td>
  <td>配信に使用する広告グループIDです。<br>※設定を解除する場合は「0」を指定してください。<br>※addのリクエストで、「0」指定は未 指定と同じ扱いになります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-<br>※データ自動 挿入の場合、Optional</td>
  <td>-<br>※データ自動 挿入の場合、Optional</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
