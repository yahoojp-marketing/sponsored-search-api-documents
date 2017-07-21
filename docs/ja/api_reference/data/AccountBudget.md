# AccountBudget
AccountBudgetオブジェクトは、広告予算を表します。
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
  <td>広告の予算金額です。<br>3000以上を指定する必要があります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>limitChargeType</td>
  <td>enum <a href="../data/LimitChargeType.md">LimitChargeType</a></td>
  <td>月額など予算に関するアカウントの種別です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>掲載開始日です。<br>「yyyyMMdd」形式で設定してください。<br>当日以降の日付を設定する必要があります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>掲載終了日です。<br>「yyyyMMdd」形式で設定してください。<br>掲載開始日以降の日付を設定する必要があります。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
