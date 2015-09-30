# NetworkTarget
NetworkTarget object describes Network coverage type.
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Target (inherited)||||||
| targetId| xsd:string| Target ID| -| Req| Req |
| type| enum <a href="./TargetType.md">TargetType</a>| Target Type| Req| Req| Req |
| NetworkTarget||||||
| networkCoverageType| enum <a href="./NetworkCoverageType.md">NetworkCoverageType</a>* |Network coverage type| Req| -| - |

*NetworkCoverageType can be set only "YAHOO_SEARCH". If you do not set the NetworkTarget, ads are delivered to the advertising system including all "YAHOO_SEARCH".

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
