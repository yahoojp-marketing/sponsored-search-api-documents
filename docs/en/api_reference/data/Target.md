# Target
Target object describes Target information.
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| targetId| xsd:string| Target ID| Req(LocationTarget),<br><br>		Ignore(ScheduleTarget, PlatformTarget, NetworkTarget)| Req| Req |
| type| enum <a href="./TargetType.md">TargetType</a>| Type| Req| Req| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
