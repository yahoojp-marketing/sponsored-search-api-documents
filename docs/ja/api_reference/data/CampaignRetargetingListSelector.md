# CampaignRetargetingListSelector
CampaignRetargetingListSelectorオブジェクトは、キャンペーン階層におけるターゲットリストの設定情報を取得するための検索条件（実行パラメータ）を保持します。

### Service
+ [CampaignRetargetingListService](../services/CampaignRetargetingListService.md)

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
  <td>アカウントIDです。</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignIds[0..1000]</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>targetListIds[0..1000]</td>
  <td>xsd:long</td>
  <td>ターゲットリストIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>excludedType</td>
  <td>enum <a href="./ExcludedType.md">ExcludedType</a></td>
  <td>配信、除外設定です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="./Paging.md">Paging</a></td>
  <td>データの取得範囲です。</td>
  <td>Optional</td>
 </tr>
</table> 
 
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
