# CampaignTargetList
CampaignTargetListオブジェクトは、特定のキャンペーンのターゲティング設定を表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req |
| targets[]| <a href="./TargetList.md">TargetList</a><br>inherited <a href="./AdScheduleTargetList.md">AdScheduleTargetList</a><br>inherited <a href="./GeoTargetList.md">GeoTargetList</a><br>inherited <a href="./NetworkTargetList.md">NetworkTargetList</a><br>inherited <a href="./PlatformTargetList.md">PlatformTargetList</a>| ターゲティング設定です。| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
