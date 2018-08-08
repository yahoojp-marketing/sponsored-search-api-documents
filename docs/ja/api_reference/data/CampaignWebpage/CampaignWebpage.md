# CampaignWebpage
CampaignWebpageオブジェクトは、キャンペーンに関連付けた除外設定の情報を保持します

### Service
+ [CampaignWebpageService](../../services/CampaignWebpageService.md)

### Namespace
[CampaignWebpageService#Namespace](../../services/CampaignWebpageService.md#namespace)


| Field | Type | Description | response | add | remove
|---|---|---|---|---|---|
| accountId| xsd: long| アカウントID | yes | Ignore | Ignore
| campaignId| xsd: long| キャンペーンID | yes | Requirement | Requirement
| campaignTrackId| xsd: long| キャンペーントラッキングID | yes | Ignore | Ignore
| webpage| [Webpage](./Webpage.md)| Webページ情報 | yes | Requirement | Requirement

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
