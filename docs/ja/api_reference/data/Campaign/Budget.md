# Budget
Budgetオブジェクトは、キャンペーン予算に関する情報を表します。

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
  <td>period</td>
  <td>enum <a href="BudgetPeriod.md">BudgetPeriod</a></td>
  <td>予算の設定期間です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>amount</td>
  <td>xsd:long</td>
  <td>1日単位のキャンペーン予算利用金額です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>deliveryMethod</td>
  <td>enum <a href="BudgetDeliveryMethod.md">BudgetDeliveryMethod</a></td>
  <td>広告の配信方法です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※Default: STANDARD</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
