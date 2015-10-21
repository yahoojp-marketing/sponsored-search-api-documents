# NegativeCampaignRetargetingListValues
NegativeCampaignRetargetingListValuesは、キャンペーンレベルでのターゲットリスト除外対象設定のget/mutateメソッドの実行結果（1 Entity）を保持するオブジェクトです。

### Service
+ [NegativeCampaignRetargetingListService](../services/NegativeCampaignRetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| ReturnValue(inherited)|||||||||
| operationSucceeded| xsd:boolean||||||| Process results. |
| error[]| <a href="./Error.md">Error</a>||||||| Details of error. |
| NegativeCampaignRetargetingListValues|||||||||
| negativeCampaignRetargetingList|<a href="./NegativeCampaignRetargetingList.md">NegativeCampaignRetargetingList</a>|1|0|○|-|-|-|Result of get/mutate method. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
