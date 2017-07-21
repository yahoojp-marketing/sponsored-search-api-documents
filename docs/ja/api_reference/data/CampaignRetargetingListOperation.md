# CampaignRetargetingListOperation
CampaignRetargetingListOperationオブジェクトは、mutateメソッドの操作対象となるキャンペーン階層のターゲットリスト設定情報を保持します。
 
### Service
+ [CampaignRetargetingListService](../services/CampaignRetargetingListService.md)

### Inheritance
+ [Operation](./Operation.md)
 
<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>operand[1..1000]</td>
  <td><a href="./CampaignRetargetingList.md">CampaignRetargetingList</a></td>
  <td>mutateメソッドの操作対象となるキャンペーン階層のターゲットリスト設定情報です。</td>
  <td>Requirement</td>
  <td>-</td>
  <td>Requirement</td>
 </tr>
 </table>
  
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
