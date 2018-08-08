# WebpageParameter
WebpageParameterは、除外設定するWebpageの条件リストを保持します。
条件リストはAND条件で適用されます。

### Service
+ [CampaignWebpageService](../../services/CampaignWebpageService.md)

### Namespace
[CampaignWebpageService#Namespace](../../services/CampaignWebpageService.md#namespace)

| Field | Type | Description | response | add | remove
|---|---|---|---|---|---|
| conditions[0..3]| [WebpageCondition](./WebpageCondition.md) | 条件リスト ※0件(未指定)は無条件  | yes | Requirement | Ignore

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
