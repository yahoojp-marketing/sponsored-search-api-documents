# Campaign
Campaign object describes Campaign information.
### Service
+ [CampaignService](../services/CampaignService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| Account ID| Req| Req| Req |
| campaignId| xsd:long| Campaign ID| -| Req| Req |
| campaignName| xsd:string| Campaign Name.| Req| Opt| - |
| userStatus| enum <a href="./UserStatus.md">UserStatus</a>| Ad Delivery status that can be set by an user.| Req| Opt| - |
| servingStatus| enum <a href="./CampaignServingStatus.md">CampaignServingStatus</a>| Delivery status in campaign level.<br>Display the campaign status, regardless of userStatus setting.| -| -| - |
| startDate| xsd:string| Campaign start date. Cannot set dates in the past.| Req| Opt| - |
| endDate| xsd:string| Campaign end date. Cannot set dates in the past or before the specified start date| Req| Opt| - |
| budget| <a href="./Budget.md">Budget</a>| Campaign budget| Req| Opt| - |
| biddingStrategyConfiguration| <a href="./BiddingStrategy_Campaign.md">BiddingStrategy</a>| Auto bidding setting| Req| Opt| - |
| biddingStrategyFailedReason| <a href="./BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a>| Reason of Auto bidding setting failure| -| -| - |
| failedBiddingStrategyConfiguration| <a href="./BiddingStrategy_Campaign.md">BiddingStrategy</a>| Failed Auto bidding configuration setting| -| -| - |
| conversionOptimizerEligibility| enum <a href="./ConversionOptimizerEligibility.md"> ConversionOptimizerEligibility </a>| Can use conversion optimizer or not| -| -| - |
| adServingOptimizationStatus| enum <a href="./AdServingOptimizationStatus.md">AdServingOptimizationStatus</a>| Setting of ad serving status optimization.(default: OPTIMIZE)| Opt| Opt| - |
| settings| <a href="./Settings.md">Settings</a><br><br>				inherited <a href="./GeoTargetTypeSetting.md">GeoTargetTypeSetting</a><br><br>				inherited <a href="./KeywordMatchSetting.md">KeywordMatchSetting</a>| Setting of Geo targeting.| Opt| Opt| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
