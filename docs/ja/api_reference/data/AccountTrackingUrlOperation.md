# AccountTrackingUrlOperation
AccountTrackingUrlOperationオブジェクトは、mutate処理の対象となるアカウントトラッキング情報と処理の内容を表します。

### Service
+ [AccountTrackingUrlService](../services/AccountTrackingUrlService.md)

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
  <td colspan="8"><a href="./Operation.md">Operation</a>(inherited)</td>
 </tr>
 <tr>
  <td>operator</td>
  <td>enum <a href="./Operator.md">Operator</a></td>
  <td>処理を表す演算子です。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">AccountTrackingUrlOperation</td>
 </tr>
 <tr>
  <td>operand[1...200]</td>
  <td><a href="./AccountTrackingUrl.md">AccountTrackingUrl</a></td>
  <td>アカウントトラッキングの配列です。<br>各配列にはmutate処理の対象となる アカウントトラッキング情報が含まれます。</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
