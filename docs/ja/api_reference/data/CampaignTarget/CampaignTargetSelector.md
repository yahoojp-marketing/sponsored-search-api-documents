# CampaignTargetSelector
CampaignTargetSelectorオブジェクトは、操作の対象とするキャンペーンのターゲティング設定を表します。
### Service
+ [CampaignTargetService](../../services/CampaignTargetService.md)

### Namespace
[CampaignTargetService#Namespace](../../services/CampaignTargetService.md#namespace)

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
  <td>campaignIds[0..500]</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>targetIds[0..500]</td>
  <td>xsd:long</td>
  <td>ターゲットIDです。</td>
  <td>Optional</td>
 </tr>
  <tr>
  <td>targetTypes[0..4]</td>
  <td>enum<br><a href="TargetType.md">TargetType</a></td>
  <td>ターゲティングの種類です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>excludedType</td>
  <td>enum<br><a href="ExcludedType.md">ExcludedType</a></td>
  <td>配信または除外設定です。<br>※targetTypesが「LOCATION(地域ターゲット)」の場合のみ利用できます。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>platformTypes</td>
  <td>enum<br><a href="PlatformType.md">PlatformType</a></td>
  <td>配信デバイスの指定です。<br>※デバイスターゲティング以外の場合はIgnore。</td>
  <td>Optional</td>
 </tr>
  <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>データの取得範囲です。</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
