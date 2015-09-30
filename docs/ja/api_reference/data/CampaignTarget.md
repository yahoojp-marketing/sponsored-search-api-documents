# CampaignTarget
CampaignTargetオブジェクトは、キャンペーンの各種ターゲティング設定を表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req| Req| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req| Req| Req |
| campaignName| xsd:string| キャンペーン名です。| -| -| - |
| target| <a href="./Target.md">Target</a><br><br> inherited <a href="./ScheduleTarget.md">ScheduleTarget</a><br><br> inherited <a href="./LocationTarget.md">LocationTarget</a><br><br> inherited <a href="./NetworkTarget.md">NetworkTarget</a><br><br> inherited <a href="./PlatformTarget.md">PlatformTarget</a>| 各種ターゲティング設定です。（時間帯、地域、ネットワーク、デバイス）| Req| Req| Req |
| bidMultiplier| xsd:double| 入札価格調整率です。| Opt| Opt| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
