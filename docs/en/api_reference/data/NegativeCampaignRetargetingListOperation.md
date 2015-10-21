# NegativeCampaignRetargetingListOperation
NegativeCampaignRetargetingListOperation is an object that holds target negative campaign retargeting in mutate methods.

### Service
+ [NegativeCampaignRetargetingListService](../services/NegativeCampaignRetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| Operation(inherited)|||||||||
| operator| enum <a href="./Operator.md">Operator</a>||||||| Operator that displays process. |
| RetargetingListOperation|||||||
| accountId| long| 1| 1| -| Req| -| Req| Account ID.|
| Operand[]| <a href="./NegativeCampaignRetargetingList.md">NegativeCampaignRetargetingList</a>| unbounded| 1| -| Req| -| Req| User list for campaign exclusion setting.|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
