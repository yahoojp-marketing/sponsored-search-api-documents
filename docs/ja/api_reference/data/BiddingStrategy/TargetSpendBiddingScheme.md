# TargetSpendBiddingScheme [BiddingStrategyService]
TargetSpendBiddingSchemeオブジェクトは、クリック数の最大化の自動入札設定情報を表します。
（BiddingStrategyService用のオブジェクトです。）
### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

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
  <td colspan="8"><a href="BiddingScheme.md">BiddingScheme</a>(inherited)</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>自動入札タイプです。</td>
  <td colspan="5"></td>
 </tr>
 <tr>
  <td colspan="8">TargetSpendBiddingScheme</td>
 </tr>
 <tr>
  <td>bidCeiling</td>
  <td>xsd:long</td>
  <td>入札価格の上限です。（0～50000）<br>※「0」が設定された場合、上限設定はありません。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>(updatable)</td>
  <td>-</td>
 </tr>
 <tr>
  <td>spendTarget</td>
  <td>xsd:long</td>
  <td>目標予算（1日あたりの予算上限）です。<br>「0」を設定した場合、目標予算は設定されません。<br>なお、setで「0」を指定すると、すでに設定済みの目標予算を解除できます。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>(updatable)</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
