# BiddingStrategyType (enum)
BiddingStrategyType displays the Auto Bidding type.
### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignService](../services/CampaignService.md)

<table>
 <tr>
  <th>Enumeration </th>
  <th>Type</th>
  <th>Description</th>
 <tr>
  <td>BUDGET_OPTIMIZER</td>
  <td>xsd:string</td>
  <td>Auto bidding without max bid setting.<br>*Currently not available.<br>*On April 12, 2017, TARGET_SPEND has been set to campaigns which this item had been set to before.</td>
 </tr>
 <tr>
  <td>MANUAL_CPC</td>
  <td>xsd:string</td>
  <td>Manual CPC settings<br>*Available in campaign level. Currently not available for ad group.</td>
 </tr>
 <tr>
  <td>PAGE_ONE_PROMOTED</td>
  <td>xsd:string</td>
  <td>Target position of search results page.<br>*Available in campaign level. Currently not available for ad group.</td>
 </tr>
 <tr>
  <td>TARGET_ROAS</td>
  <td>xsd:string</td>
  <td>Target ROAS.<br>*Available on updating campaign process. Currently not available for ad group.</td>
 </tr>
 <tr>
  <td>TARGET_SPEND</td>
  <td>xsd:string</td>
  <td>Maximize Clicks.<br>*Applicable for campaign. Currently not available for ad group.</td>
 </tr>
 <tr>
  <td>ENHANCED_CPC</td>
  <td>xsd:string</td>
  <td>Maximize conversions.<br>*Applicable for campaign. Currently not available for ad group.</td>
 </tr>
 <tr>
  <td>TARGET_CPA</td>
  <td>xsd:string</td>
  <td>Target conversion spend (CPA).<br>*Available on updating campaign process. Currently not available for ad group.</td>
 </tr>
 <tr>
  <td>NONE</td>
  <td>xsd:string</td>
  <td>Specify this item to cancel the Auto bidding, and follow the strategy of upper level entity.<br>*Available when removing bid setting on ad group and/or keyword level.</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
