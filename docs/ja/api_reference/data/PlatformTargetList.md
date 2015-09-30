# PlatformTargetList
PlatformTargetオブジェクトは、デバイス設定を表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignId| xsd:string| キャンペーンIDです。 |
| type| enum <a href="../data/TargetType.md">TargetType</a>| ターゲットタイプです。 |
| targets[]| <a href="../data/PlatformTarget.md">PlatformTarget</a>| ターゲットです。SMART_PHONEに関する設定しかできません。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
