# CampaignTarget
CampaignTarget describes each type of targeting setting of Campaign.
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| Account ID| Req| Req| Req |
| campaignId| xsd:long| Campaign ID| Req| Req| Req |
| campaignName| xsd:String| Campaign Name| -| -| - |
| target| <a href="./Target.md">Target</a><br><br><br>			inherited <a href="./ScheduleTarget.md">ScheduleTarget</a><br><br><br>			inherited <a href="./LocationTarget.md">LocationTarget</a><br><br><br>			inherited <a href="./NetworkTarget.md">NetworkTarget</a><br><br><br>			inherited <a href="./PlatformTarget.md">PlatformTarget</a><br>| Targeting Setting (Hour, Geo, Network, device)| Req| Req| Req |
| bidMultiplier| xsd:double| Bid multiplier| Opt| Opt| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
