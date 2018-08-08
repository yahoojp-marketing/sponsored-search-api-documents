
# WebpageCondition
WebpageConditionオブジェクトは、Webpageの条件を保持します。

### Service
+ [CampaignWebpageService](../../services/CampaignWebpageService.md)

### Namespace
[CampaignWebpageService#Namespace](../../services/CampaignWebpageService.md#namespace)


| Field | Type | Description | response | add | remove
|---|---|---|---|---|---|
|type| [WebpageConditionType](./WebpageConditionType.md) | 除外設定する種別 ※「ALL_PAGES」は指定不可 | yes | Requirement | Ignore
|argument| xsd:string | 条件の設定値(正規表現の指定可) | yes | Requirement | Ignore

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
