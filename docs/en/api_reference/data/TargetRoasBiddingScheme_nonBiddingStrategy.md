# TargetRoasBiddingScheme [Non-BiddingStrategyService]
TargetRoasBiddingScheme object displays Auto Bidding setting for Target ROAS. (This is for services other than BiddingStrategyService)
### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignService](../services/CampaignService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| BiddingSchema(inherited)||||||
| biddingStrategyType| enum <a href="../data/BiddingStrategyType.md">BiddingStrategyType</a>| Auto bidding type.| Req| Req<br>                        (notupdatable)| ─ |
| TargetRoasBiddingScheme||||||
| targetRoas| xsd:double| Target ROAS<br>*Setting limit: 0.01 〜1000.00（1%〜100000%）<br>*ROAS: Return On Average Spend| ─| ─| ─ |
| bidCeiling| xsd:long| CPC limit (0-50000) <br>*No limits if numbers are set "0"| ─| ─| ─ |
| bidFloor| xsd:long| Minimum CPC <br>*Set "0" to deactivate| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
