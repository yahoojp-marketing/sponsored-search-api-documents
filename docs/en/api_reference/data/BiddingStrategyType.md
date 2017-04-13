# BiddingStrategyType (enum)
BiddingStrategyType displays the Auto Bidding type.
### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignService](../services/CampaignService.md)

| Enumeration | type| Description | 
|---|---|---|
| BUDGET_OPTIMIZER| string| Auto bidding without max bid setting. Currently not available.<br>*On April 12, 2017, TARGETSPEND has been set to campaigns which this item had been set to before. |
| MANUAL_CPC| string|  Manual CPC settings<br>*Available in campaign, ad group, and/or keyword |
| PAGE_ONE_PROMOTED| string|  Target position of search page results<br>*Available in campaign and/or ad group |
| TARGET_ROAS|  string| Target ROAS<br>*Available in campaign and/or ad group<br>**ROAS = Return On Average Spend |
| TARGET_SPEND| string|  Maximize Click<br>*Available in campaign and/or ad group |
| ENHANCED_CPC| string|  Enhanced CPC<br>*Available in campaign and/or ad group |
| TARGET_CPA| string|  Target conversion spend<br>*Available in campaign and/or ad group |
| NONE| string|  Cancel the Auto bidding, and follow the strategy of upper level entity<br>*Available when ad group and/or keyword level are canceled |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
