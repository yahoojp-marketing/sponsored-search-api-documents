# AdGroupBidMultiplierSelector
AdGroupBidMultiplierSelectorオブジェクトは、入札価格調整率を格納するコンテナです。

### Service
+ [AdGroupBidMultiplierService](../../services/AdGroupBidMultiplierService.md)

### Namespace
[AdGroupBidMultiplierService#Namespace](../../services/AdGroupBidMultiplierService.md#namespace)

| フィールド | データ型 | 説明 |
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignIds[0..1000]| xsd:long| キャンペーンIDです。 |
| adGroupIds[0..1000]| xsd:long| 広告グループIDです。 |
| platformTypes[0..3]| enum <br><a href="PlatformType.md">PlatformType</a>| 配信デバイスです。 |
| paging| <a href="../Common/Paging.md">Paging</a>| ページングです。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
