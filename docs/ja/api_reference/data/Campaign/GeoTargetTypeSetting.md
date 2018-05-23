# GeoTargetTypeSetting
GeoTargetTypeSettingsオブジェクトは、地域ターゲットの情報を格納するコンテナです。

### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

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
  <td colspan="8"><a href="Settings.md">Settings</a>(inherited)</td>
 </tr>
 <tr>
  <td>type</td>
  <td>enum <a href="SettingType.md">SettingType</a></td>
  <td>ターゲット及びマッチング設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>Default: GEO_TARGET_TYPE_SETTING</td>
  <td>Requirement<br><i>NotUpdatable</i></td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">GeoTargetTypeSetting</td>
 </tr>
 <tr>
  <td>positiveGeoTargetType</td>
  <td>enum <a href="GeoTargetType.md">GeoTargetType</a></td>
  <td>キャンペーンで使用するターゲット地域の設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>Default: DONT_CARE</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>negativeGeoTargetType</td>
  <td>enum <a href="GeoTargetType.md">GeoTargetType</a></td>
  <td>キャンペーンで使用する除外地域の設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>Default: LOCATION_OF_PRESENCE</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
