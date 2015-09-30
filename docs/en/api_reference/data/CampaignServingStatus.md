# CampaignServingStatus (enum)
CampaignServingStatus displays delivery status in campaign level.
Display the campaign status, regardless of userStatus setting.
### Service
+ [CampaignService](../services/CampaignService.md)

| Enumeration | Description | 
|---|---|
| SERVING| The campaign is currently serving ads. |
| ENDED| The campaign has ended.<br>It is already past the delivery period, so the campaign is currently not serving ads. |
| PENDING| The campaign has not started.<br>It has not reached the delivery period, so the campaign is currently not serving ads. |
| STOP| The campaign has been suspended.<br>(Reason may from lack of allocated funds) |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
