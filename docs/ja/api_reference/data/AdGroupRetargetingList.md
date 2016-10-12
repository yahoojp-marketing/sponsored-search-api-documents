# AdGroupRetargetingList
AdGroupRetargetingListは、広告グループレベルでのターゲットリスト設定を保持するオブジェクトです。

### Service
+ [AdGroupRetargetingListService](../services/AdGroupRetargetingListService.md)

| Field | Type | response | get | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| accountId| xsd:long|yes|-|-|-|-| アカウントIDです。 |
| campaignId| xsd:long|yes|-|Requirement|Requirement|Requirement| キャンペーンIDです。 |
| campaignName| xsd:string|yes|-|-|-|-| キャンペーン名です。 |
| adGroupId| xsd:long|yes|-|Requirement|Requirement|Requirement| 広告グループIDです。 |
| adGroupName| xsd:string|yes|-|-|-|-| 広告グループ名です。 |
| criterionTargetList| <a href="./CriterionTargetList.md">CriterionTargetList</a>|yes|-|Requirement|Requirement|Requirement| ターゲットリストです。 |
| excludedType|enum <a href="./ExcludedType_AdGroupRetargetingList.md">ExcludedType</a>|yes|-|Optional|Optional|Requirement| 包含/追加設定です。<br>※Default値：INCLUDED |
| bidMultiplier| xsd:double|yes|-|Optional|Optional|-| MaxCPC上昇値です。<br>※Default値：1.00 |


<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
