# NegativeCampaignRetargetingList
NegativeCampaignRetargetingListは、キャンペーンレベルでのターゲットリスト除外対象設定を保持するオブジェクトです。

### Service
+ [NegativeCampaignRetargetingListService](../services/NegativeCampaignRetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 0| ○| Ignore| -| Ignore| Account ID. |
| campaignId| long| 1| 1| ○| Req| -| Req| Campaign ID. |
| campaignName| string| 1| 0| ○| Ignore| -| Ignore| Campaign name. |
| criterionTargetList| <a href="./CriterionTargetList.md">CriterionTargetList</a>| 1| 1| ○| Req| -| Req| Target list. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
