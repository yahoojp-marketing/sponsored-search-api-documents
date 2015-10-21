# LogicalTargetList
LogicalTargetList is an object that holds the combination target list information.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| TargetingList(inherited)|||||||
| accountId|long| 1| 1| ○| Req| Req| -| Account ID. |
| retargetingAccountStatus| <a href="./RetargetingAccountStatus.md">RetargetingAccountStatus</a>| 1| 0| ○| Ignore| Ignore| -| Retargeting account status. |
| targetListid| long| 1| 0| ○| Ignore| Req| -| Target list ID. |
| targetListType| enum <a href="./TargetListType.md">TargetListType</a>| 1| 1| ○| Req| Req| -| Target list type. |
| targetListName| string| 1| 0| ○| Req| Opt| -| Target list name. |
| targetListDescription|string| 1| 0| ○| Opt| Opt| -| Description of target list. |
| reachStorageStatus| enum <a href="./ReachStorageStatus.md">ReachStorageStatus</a>| 1| 0| ○| Optional<br>*Ignore for LogicalTargetList| Optional<br>*Ignore for LogicalTargetList| -| Flag status to hold Cookie.<br> Default: OPEN|
| reachStorageSpan| long| 1| 0| ○| Optional<br>*Ignore for LogicalTargetList| Optional<br>*Ignore for LogicalTargetList| -|Days to hold Cookie.<br>*Default: 180|
| reach| long| 1| 0| ○| Ignore| Ignore| -| Number of users stored to the list. |
| LogicalTargetList|||||||
| logicalGroup| <a href="./LogicalGroup.md">LogicalGroup</a>| 20| 1| ○| Req| Req| -| Combination group.|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
