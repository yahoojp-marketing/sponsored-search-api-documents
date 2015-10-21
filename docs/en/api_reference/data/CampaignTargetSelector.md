# CampaignTargetSelector
Campaign target settings.

### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| Field | Data Type | Description | 
|---|---|---|
| accountId| xsd:long| Account ID |
| campaignIds[]| xsd:long| Campaign ID. |
| targetIds[]| xsd:string| TargetId. |
| targetTypes[]| enum <a href="./TargetType.md">TargetType</a>| TargetTypes. |
| excludedType| enum <a href="./ExcludedType_CampaignTarget.md">ExcludedType</a>| ExcludedType. |
| paging| <a href="./Paging.md">Paging</a>| Holds the paging parameters such as starting index. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
