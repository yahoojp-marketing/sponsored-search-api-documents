# ConversionTrackerPage
ConversionTrackerPageオブジェクトは、取得されるコンバージョントラッカー情報のエントリーを表します。

### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

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
  <td colspan="8"><a href="../Common/Page.md">Page</a>(inherited)</td>
 </tr>
 <tr>
  <td colspan="8">ConversionTrackerPage</td>
 </tr>
 <tr>
  <td>totalConversions</td>
  <td>xsd:long</td>
  <td>自動入札設定の対象コンバージョン数の合計です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>totalConversionValue</td>
  <td>xsd:string</td>
  <td>自動入札設定の対象コンバージョン値の合計です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>

 <tr>
  <td>totalAllConversions</td>
  <td>xsd:long</td>
  <td>自動入札設定の対象コンバージョン数と、対象外コンバージョン数の合計です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>totalAllConversionValue</td>
  <td>xsd:string</td>
  <td>自動入札設定の対象コンバージョン値と、対象外コンバージョン値の合計です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>

 <tr>
  <td>Values[0..200]</td>
  <td><a href="ConversionTrackerValues.md">ConversionTrackerValues</a></td>
  <td>コンバージョントラッカー情報です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
