# CampaignOperation
CampaignOperation object displays target campaign information and its operation results.
### Service
+ [CampaignService](../services/CampaignService.md)

| Field | Data Type | Description | 
|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| Operator. This field is required and should not be null.| Req |
| CampaignOperation||||
| accountId| xsd:long| Account ID| Req |
| operand[]| <a href="./Campaign.md">Campaign</a>| List of campaign.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
