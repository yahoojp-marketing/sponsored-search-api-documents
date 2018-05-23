# NetworkTarget
NetworkTargetオブジェクトは、広告掲載方式を表します。
### Service
+ [CampaignTargetService](../../services/CampaignTargetService.md)

### Namespace
[CampaignTargetService#Namespace](../../services/CampaignTargetService.md#namespace)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE |
|---|---|---|---|---|---|
| Target (inherited)||||||
| targetId| xsd:string| ターゲットIDです。| -| Req| Req |
| type| enum <a href="TargetType.md">TargetType</a>| ターゲットTypeです。| Req| Req| Req |
| NetworkTarget||||||
| networkCoverageType(notupdatable)| enum <a href="NetworkCoverageType.md">NetworkCoverageType</a>※| 広告掲載方式です。| Req| -| - |
※：NetworkCoverageTypeでは、「YAHOO_SEARCH」のみ設定可能です。<br>
なおNetworkTargetを設定しない場合、「YAHOO_SEARCH」を含むすべての広告掲載方式に広告は配信されます。<br>
<br>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
