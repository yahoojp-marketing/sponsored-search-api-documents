# Location
Locationオブジェクトは、地域設定情報を格納します。

### Service
+ [FeedItemService](../services/FeedItemService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>targetId</td>
  <td>xsd:string</td>
  <td>地域種別コードです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>type</td>
  <td>enum<br><a href="./CriterionTypeFeedItem.md">CriterionTypeFeedItem</a></td>
  <td>クライテリオンタイプです。</td>
  <td>yes</td>
  <td>Optional<br>※default：LOCATION</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>geoTargetingRestriction</td>
  <td>enum<br><a href="./FeedItemGeoRestriction.md">FeedItemGeoRestriction</a></td>
  <td>地域設定の配信を制御します。</td>
  <td>yes</td>
  <td>Optional<br>※default：NONE</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>

 <tr>
  <td>isRemove</td>
  <td>enum<br><a href="./IsRemove.md">IsRemove</a></td>
  <td>削除フラグです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>※地域設定を解除する場合は、isRemoveにTRUEを指定します。<br>解除後は、geoTargetingRestrictionにNONEが設定されます。</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
