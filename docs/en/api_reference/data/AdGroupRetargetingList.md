# AdGroupRetargetingList
AdGroupRetargetingList is an object that holds ad group user list information.

### Service
+ [AdGroupRetargetingListService](../services/AdGroupRetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Ignore| Ignore| Ignore| Account ID. |
| campaignId| long| 1| 1| ○| Req| Req| Req| Campaign ID. |
| campaignName| string| 1| 0| ○| Ignore| Ignore| Ignore| Campaign name. |
| adGroupId| long| 1| 1| ○| Req| Req| Req| Ad group ID. |
| adGroupName| string| 1| 0| ○| Ignore| Ignore| Ignore| Ad group name. |
| criterionTargetList| <a href="./CriterionTargetList.md">CriterionTargetList</a>| 1| 1| ○| Req| Req| Req| Target list. |
| excludedType|enum <a href="./ExcludedType_AdGroupRetargetingList.md">ExcludedType</a>| 1| 0| ○| Opt| Opt| Req| Setting of target status<br>* Default: INCLUDED|
| bidMultiplier| double| 1| 0| ○| Opt| Opt| Ignore| Maximum CPC increase value.<br>* Default: 1.00|
| targetAll| enum <a href="./TargetAll.md">TargetAll</a>| 1|0| ○| Opt| Opt| Ignore| All users target setting.<br>* Default: DEACTIVE|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
