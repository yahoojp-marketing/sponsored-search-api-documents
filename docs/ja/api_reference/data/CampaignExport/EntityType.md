# EntityType (enum)
EntityTypeは、対象となるエンティティを表します。<br>
※リクエスト時はEntityTypeで定義されている値をString型で指定します。<br>
※レスポンスの値はenumとして返却されます。

### Service
+ [CampaignExportService](../../services/CampaignExportService.md)

### Namespace
[CampaignExportService#Namespace](../../services/CampaignExportService.md#namespace)

<table>
 <tr>
  <th>Enumeration</th>
  <th>Type</th>
  <th>Description</th>
 <tr>
  <td>CAMPAIGN</td>
  <td>xsd:string</td>
  <td>キャンペーン</td>
 </tr>
 <tr>
  <td>NEGATIVE_CAMPAIGN_CRITERION</td>
  <td>xsd:string</td>
  <td>対象外キーワード（キャンペーンレベル）</td>
 </tr>
 <tr>
  <td>AD_GROUP</td>
  <td>xsd:string</td>
  <td>広告グループ</td>
 </tr>
 <tr>
  <td>BIDDABLE_AD_GROUP_CRITERION</td>
  <td>xsd:string</td>
  <td>入札キーワード</td>
 </tr>
 <tr>
  <td>NEGATIVE_AD_GROUP_CRITERION</td>
  <td>xsd:string</td>
  <td>対象外キーワード（広告グループレベル）</td>
 </tr>
 <tr>
  <td>AD</td>
  <td>xsd:string</td>
  <td>広告</td>
 </tr>
 <tr>
  <td>ALL</td>
  <td>xsd:string</td>
  <td>すべての広告エンティティ</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
