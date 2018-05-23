# CampaignExportValues
CampaignExportValuesオブジェクトは、addJob/get操作の実行結果（1 Entity）を含むジョブ情報を表します。

### Service
+ [CampaignExportService](../../services/CampaignExportService.md)

### Namespace
[CampaignExportService#Namespace](../../services/CampaignExportService.md#namespace)

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
  <td colspan="8"><a href="../Common/ReturnValue.md">ReturnValue</a>(inherited)</td>
 </tr>
 <tr>
  <td>operationSucceeded</td>
  <td>xsd:boolean</td>
  <td>処理結果を表示します。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td>error[0...n]</td>
  <td><a href="../Common/Error.md">Error</a></td>
  <td>エラーの内容です。</td>
  <td colspan="7"></td>
 </tr>
 <tr>
  <td colspan="8">CampaignExportValues</td>
 </tr>
 <tr>
  <td>job</td>
  <td><a href="Job.md">Job</a></td>
  <td>1ジョブのaddJob/get 操作の実行結果です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
