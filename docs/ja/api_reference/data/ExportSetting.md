# ExportSetting
ExportSetting オブジェクトは、エクスポートする条件を表します。

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
  <td>アカウントIDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignIds[0...500]</td>
  <td>xsd:long</td>
  <td>ダウンロード対象のキャンペーンIDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignCriterionIds[0...500]</td>
  <td>xsd:long</td>
  <td>キャンペーンクライテリアIDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupIds[0...500]</td>
  <td>xsd:long</td>
  <td>ダウンロード対象の広告グループIDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adIds[0...500]</td>
  <td>xsd:long</td>
  <td>ダウンロード対象の広告IDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupCriterionIds[0...500]</td>
  <td>xsd:long</td>
  <td>広告グループクライテリアIDです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>ダウンロード対象のキャンペーン配信 ステータスです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>ダウンロード対象の広告グループ配信 ステータスです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupAdUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>ダウンロード対象の広告配信 ステータスです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupCriterionUserStatuses[0...2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>ダウンロード対象の広告グループ クライテリア配信ステータスです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
<tr>
  <td>adGroupAdApprovalStatuses[0...5]</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>ダウンロード対象の広告審査 ステータスです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupCriterionApprovalStatuses[0...5]</td>
  <td>enum <a href="./ApprovalStatus.md">ApprovalStatus</a></td>
  <td>ダウンロード対象のキーワード審査 ステータスです。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>entityTypes[0...7]</td>
  <td>enum <a href="./EntityType_CampaignExport.md">EntityType</a></td>
  <td>ダウンロードするエンティティの単位です。</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>jobName</td>
  <td>xsd:string</td>
  <td>ダウンロードするジョブの名称です。<br>※Default：NULL</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>lang</td>
  <td>enum <a href="./Lang.md">Lang</a></td>
  <td>ダウンロードする情報の言語設定です。<br>※Default：JA</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>output</td>
  <td>enum <a href="./Output.md">Output</a></td>
  <td>ダウンロードする情報の出力形式 設定です。</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>encoding</td>
  <td>enum <a href="./Encoding.md">Encoding</a></td>
  <td>ダウンロードする情報の文字エンコード 設定です。</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advanced</td>
  <td>enum <a href="./Advanced.md">Advanced</a></td>
  <td>エクスポート対象のオブジェクトの種類を 選択します。<br>※Default：TRUE</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
