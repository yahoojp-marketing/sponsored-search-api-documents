# AccountBudget
AccountBudget object describes Budget for advertising on the account.
### Service
+ [AccountService](../services/AccountService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>amount</td>
  <td>xsd:long</td>
  <td>Amount of budeget. <br>The amount have to be specified over 3000JPY.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>limitChargeType</td>
  <td>enum <a href="../data/LimitChargeType.md">LimitChargeType</a></td>
  <td>Type of payment for the Account, such as monthly budget.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>Start date of ad serving.<br>It has to be specified in 'yyyyMMdd' format.<br>This date have to be after the opearing day.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>End date of ad serving.<br>It has to be specified in 'yyyyMMdd' format.<br>This date have to be after Start date.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
