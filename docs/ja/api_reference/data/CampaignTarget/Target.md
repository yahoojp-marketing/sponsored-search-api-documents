# Target
Targetオブジェクトは、ターゲティング設定を表します。
### Service
+ [CampaignTargetService](../../services/CampaignTargetService.md)

### Namespace
[CampaignTargetService#Namespace](../../services/CampaignTargetService.md#namespace)

| Field | Data Type | Description | response| get| add | set | remove |
|---|---|---|---|---|---|---|---|
| targetId| xsd:string| ターゲットIDです。| yes | - |Requirement<br>※LocationTargetの場合のみ。<br>ScheduleTarget、PlatformTarget、NetworkTargetの場合はIgnore| Requirement<br>※PlatformTargetの場合はIgnore| Requirement <br>NotUpdatable| Requirement <br>NotUpdatable|
| type| enum <a href="TargetType.md">TargetType</a>| ターゲットタイプです。| yes | - |Requirement | Requirement <br>NotUpdatable |Requirement <br>NotUpdatable|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
