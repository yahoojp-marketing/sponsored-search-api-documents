# CampaignWebpageSelector
CampaignWebpageSelectorオブジェクトは、getで取得する条件を保持します。
### Service
+ [CampaignWebpageService](../../services/CampaignWebpageService.md)

### Namespace
[CampaignWebpageService#Namespace](../../services/CampaignWebpageService.md#namespace)

| Field | Type | Description |
|---|---|---|
| accountId| xsd: long| アカウントID |
| campaignIds[0..1000]| xsd: long | キャンペーンID |
| targetIds[0..1000]| xsd: long | 除外設定を識別するID |
| paging| <a href="../Common/Paging.md">Paging</a>| レスポンス件数 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
