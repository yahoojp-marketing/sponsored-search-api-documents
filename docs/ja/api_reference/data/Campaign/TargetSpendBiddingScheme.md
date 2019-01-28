# TargetSpendBiddingScheme [Non-BiddingStrategyService]
TargetSpendBiddingSchemeオブジェクトは、クリック数の最大化の自動入札設定情報を表します。<br>
（BiddingStrategyService以外用のオブジェクトです。）

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
  <td colspan="8"><a href="BiddingScheme.md">BiddingScheme</a>(inherited)</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>自動入札タイプです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">TargetSpendBiddingScheme</td>
 </tr>
  <tr>
  <td>bidCeiling</td>
  <td>xsd:long</td>
  <td>入札価格の上限<br>※制限値：0 ～ 50000<br>※「0」が設定された 場合、上限設定は ありません。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>Default : 0</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>spendTarget</td>
  <td>xsd:long</td>
  <td>目標予算の上限</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>Default : 0</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
