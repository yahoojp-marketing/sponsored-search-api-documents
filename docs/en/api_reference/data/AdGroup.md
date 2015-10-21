# AdGroup
AdGroup object displays ad group information.
### Service
+ [AdGroupService](../services/AdGroupService.md)

| Field | Data Type | Description | add | set | remove | 
|---|---|---|---|---|---|
| accountId| xsd:long| Account ID| Req| Req<br>NotUpdatable| Req<br>NotUpdatable |
| campaignId| xsd:long| ID of the campaign with which this ad group is associated.| Req| Req<br>NotUpdatable| Req<br>NotUpdatable |
| campaignName| xsd:string| Name of the campaign with which this ad group is associated.| Ignore| Ignore<br>NotUpdatable| IgnoreNotUpdatable |
| adGroupId| xsd:long| AdGroup id This field is read only.| Ignore| Req<br>NotUpdatable| Req<br>NotUpdatable |
| adGroupName| xsd:string| Name of this ad group.| Req| Opt<br>Updatable| Ignore<br>NotUpdatable |
| userStatus| enum <a href="./UserStatus.md">UserStatus</a>| Status of the ad group.| Req| Opt<br>Updatable| - |
| biddingStrategyConfiguration| <a href="./BiddingStrategy_AdGroup.md">BiddingStrategy</a>| Auto bidding setting<br>* Reference only for BudgetOptimizer.<br>* Set "NONE" in biddingStrategyType to avoid Auto bidding setting.<br>* This will apply upper class Auto bidding as a default.| Opt| OptUpdatable| - |
| biddingStrategyFailedReason| <a href="./BiddingStrategyFailedReason.md"> BiddingStrategyFailedReason </a>| Reason of Auto bidding failure<br>* Display only when failure occurs| -| -| - |
| failedBiddingStrategyConfiguration| <a href="./BiddingStrategy_AdGroup.md">BiddingStrategy</a>| Failure of Auto bidding<br>*Display only when failure occurs| -| -| - |
| settings| <a href="./Settings_AdGroup.md">Settings</a> <br>inherited <a href="./TargetingSetting.md">TargetingSetting</a>| Target setting| Opt| Opt| - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
