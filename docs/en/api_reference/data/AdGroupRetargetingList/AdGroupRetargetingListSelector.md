# AdGroupRetargetingListSelector
AdGroupRetargetingListSelector is an object that holds search condition (parameter) of get method.

### Service
+ [AdGroupRetargetingListService](../../services/AdGroupRetargetingListService.md)

### Namespace
[AdGroupRetargetingListService#Namespace](../../services/AdGroupRetargetingListService.md#namespace)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| -| -| -| -| Account ID. |
| campaignIds[]| long| unbounded| 0| -| -| -| -| Campaign ID. |
| targetListIds[]| long| unbounded| 0| -| -| -| -| Target list ID. |
| adGroupIds[]| long| unbounded| 0| -| -| -| -| Ad group ID. |
| excludedType[]| enum <a href="ExcludedType_AdGroupRetargetingList.md">ExcludedType</a>| 1| 0| -| -| -| -| Status of target. |
| paging| <a href="../Common/Paging.md">Paging</a>| 1| 0| -| -| -| -| Paging. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
