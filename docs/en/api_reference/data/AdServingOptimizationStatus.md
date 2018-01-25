# AdServingOptimizationStatus (enum)
AdServingOptimizationStatus describes optimization setting of ad serving.
### Service
+ [CampaignService](../services/CampaignService.md)

<table>
 <tr>
  <th>Enumeration </th>
  <th>Type</th>
  <th>Description</th>
 <tr>
  <td>OPTIMIZE</td>
  <td>xsd:string</td>
  <td>Ad serving is optimized based on CTR for the campaign. <br>Highly effective ad creative is served preferentially.<br>*On creating a new campaign, the value 'OPTIMIZE' is set to this item in call cases.</td>
 </tr>
 <tr>
  <td>ROTATE</td>
  <td>xsd:string</td>
  <td>Ads will evenly rotated for 90 days, then will be set up to optimize based on CTR.<br>*This option is currently not available for setting.</td>
 </tr>
 <tr>
  <td>ROTATE_INDEFINITELY</td>
  <td>xsd:string</td>
  <td>Ads will evenly rotated on a continuous basis. (not optimized)<br>*This option is currently not available for setting.</td>
 </tr>
 <tr>
  <td>CONVERSION_OPTIMIZE</td>
  <td>xsd:string</td>
  <td>Ad serving is optimized based on conversions.<br>*This option is currently not available for setting.</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
