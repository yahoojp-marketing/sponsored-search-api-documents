# CampaignWebpageOperation
CampaignWebpageOperationオブジェクトは、mutateメソッドで操作対象となるPageFeedItemの除外設定を保持します。

### Service
+ [CampaignWebpageService](../../services/CampaignWebpageService.md)

### Namespace
[CampaignWebpageService#Namespace](../../services/CampaignWebpageService.md#namespace)

| Field | Type | Description |
|---|---|---|
| accountId| xsd: long| アカウントID |
| operand[1..2000]| [CampaignWebpage](./CampaignWebpage.md) | 登録または削除対象のPageFeedItemの除外設定 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
