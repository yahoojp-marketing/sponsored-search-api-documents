# AdGroupRetargetingList
AdGroupRetargetingList is an object that holds ad group user list information.

### Service
+ [AdGroupRetargetingListService](../services/AdGroupRetargetingListService.md)

| field | type | response | get | add | set | remove | description | 
|---|---|---|---|---|---|---|---|
| accountId| xsd:long| yes| - | -| -| -| Account ID. |
| campaignId| xsd:long| yes| - | Req| Req| Req| Campaign ID. |
| campaignName| xsd:string| yes| - | -| -| -| Campaign name. |
| adGroupId| xsd:long| yes| -| Req | Req| Req| Ad group ID. |
| adGroupName| xsd:string| yes| - | -| -| -| Ad group name. |
| criterionTargetList| <a href="./CriterionTargetList.md">CriterionTargetList</a>| yes| -| Req| Req| Req| Target list. |
| excludedType|enum <a href="./ExcludedType_AdGroupRetargetingList.md">ExcludedType</a>| yes| -| Opt| Opt| Req| Setting of target status<br>* Default: INCLUDED|
| bidMultiplier| xsd:double| yes| -| Opt| Opt| -| Maximum CPC increase value.<br>* Default: 1.00|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
