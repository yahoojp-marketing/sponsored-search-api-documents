# RuleBaseTargetList
RuleBaseTargetList is an object that holds Rule based target list information.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| TargetingList(inherited)|||||||||
| accountId|long| 1| 1| ○| Req| Req| -| Account ID. |
| retargetingAccountStatus| <a href="./RetargetingAccountStatus.md">RetargetingAccountStatus</a>| 1| 0| ○| Ignore| Ignore| -| Retargeting account status. |
| targetListid| long| 1| 0| ○| Ignore| Req| -| Target list ID. |
| targetListType| enum <a href="./TargetListType.md">TargetListType</a>| 1| 1| ○| Req| Req| -| Target list type. |
| targetListName| string| 1| 0| ○| Req| Opt| -| Target list name. |
| targetListDescription|string| 1| 0| ○| Opt| Opt| -| Description of target list. |
| reachStorageStatus| enum <a href="./ReachStorageStatus.md">ReachStorageStatus</a>| 1| 0| ○| Optional<br>*Ignore for LogicalTargetList| Optional<br>*Ignore for LogicalTargetList| -| Flag status to hold Cookie.<br> Default: OPEN|
| reachStorageSpan| long| 1| 0| ○| Optional<br>*Ignore for LogicalTargetList| Optional<br>*Ignore for LogicalTargetList| -|Days to hold Cookie.<br>*Default: 180|
| reach| long| 1| 0| ○| Ignore| Ignore| -| Number of users stored to the list. |
| RuleBaseTargetList|||||||
| rules[]|string|20|0|○|Opt|Opt|-|Rule setting.|
| isAllVisitor|enum <a href="./IsAllVisitorRule.md">IsAllVisitorRule</a>|1|0|○|Req|Req|-|All visitor rules setting.|
| isDateSpecific|enum <a href="./IsDateSpecificRule.md">IsDateSpecificRule</a>|1|0|○|Opt|Ignore|-|Rule with specific deadline date.|
| startDate|string|1|0|○|Opt|Opt|-|Start date of rule setting.<br>* In yyyyMMdd format.<br>* Request date can be set up to 2037/12/30.|
| endDate|string|1|0|○|Opt|Opt|-|End date of rule setting.<br>* In yyyyMMdd format.<br>* Request date can be set up to 2037/12/30.|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>


