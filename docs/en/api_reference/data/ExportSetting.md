# ExportSetting
ExportSetting object describes the condition for exports.

### Service
+ [CampaignExportService](../services/CampaignExportService.md)

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID</td>
  <td>-</td>
  <td>Required</td>
  <td>Required</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignIds[0...500]</td>
  <td>xsd:long</td>
  <td>Campaign ID of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignCriterionIds[0...500]</td>
  <td>xsd:long</td>
  <td>Campaign criteria ID</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupIds[0...500]</td>
  <td>xsd:long</td>
  <td>Ad group ID of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adIds[0...500]</td>
  <td>xsd:long</td>
  <td>Ad ID of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupCriterionIds[0...500]</td>
  <td>xsd:long</td>
  <td>Ad group criteria ID</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>Distribution status in campaign of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>Distribution status in ad group of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupAdUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>Distribution status in ad of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupCriterionUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>Distribution status in ad group criteria of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupAdApprovalStatuses[0...5]</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Status in ad approval of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>adGroupCriterionApprovalStatuses[0...5]</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Status in keyword approval of export objective</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>entityTypes[0...6]</td>
  <td>enum <a href="./EntityType_CampaignExport.md">EntityType</a></td>
  <td>Entity type to download</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>&lowast;Default: ALL</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>jobName</td>
  <td>xsd:string</td>
  <td>Job information for export</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>&lowast;Default: NULL</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>lang</td>
  <td>enum <a href="./Lang.md">Lang</a></td>
  <td>Language setting for export</td>
  <td>-</td>
  <td>Required</td>
  <td>Optional<br>&lowast;Default: JA</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>output</td>
  <td>enum <a href="./Output.md">Output</a></td>
  <td>Output format for export</td>
  <td>-</td>
  <td>Required</td>
  <td>Optional<br>&lowast;Default: CSV</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>encoding</td>
  <td>enum <a href="./Encoding.md">Encoding</a></td>
  <td>Encoding setting of export</td>
  <td>-</td>
  <td>Required</td>
  <td>Optional<br>&lowast;Default: UTF-8</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>exportFields[0..n]</td>
  <td>xsd:string</td>
  <td>Select which field to export.</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
