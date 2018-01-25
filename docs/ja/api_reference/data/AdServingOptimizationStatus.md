# AdServingOptimizationStatus (enum)
AdServingOptimizationStatusは、広告表示の最適化設定を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

<table>
 <tr>
  <th>Enumeration </th>
  <th>Type</th>
  <th>Description</th>
 <tr>
  <td>OPTIMIZE</td>
  <td>xsd:string</td>
  <td>広告表示の最適化が設定されています。<br>効果の高い広告が優先的に表示されます。<br>※キャンペーンの新規作成時は一律「OPTIMIZE」が設定されます。</td>
 </tr>
 <tr>
  <td>ROTATE</td>
  <td>xsd:string</td>
  <td>広告は90日間均一に配信され、その後最適化するように設定されます。<br>※現在は設定できません。</td>
 </tr>
 <tr>
  <td>ROTATE_INDEFINITELY</td>
  <td>xsd:string</td>
  <td>広告は常に均一に配信されます（最適化しません）。<br>※現在は設定できません。</td>
 </tr>
 <tr>
  <td>CONVERSION_OPTIMIZE</td>
  <td>xsd:string</td>
  <td>コンバージョン最適に基づいて配信されます。<br>※現在は設定できません。</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
