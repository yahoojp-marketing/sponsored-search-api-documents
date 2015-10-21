# NegativeCampaignRetargetingListValues
NegativeCampaignRetargetingListValuesは、キャンペーンレベルでのターゲットリスト除外対象設定のget/mutateメソッドの実行結果（1 Entity）を保持するオブジェクトです。

### Service
+ [NegativeCampaignRetargetingListService](../services/NegativeCampaignRetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| ReturnValue(inherited)|||||||||
| operationSucceeded| xsd:boolean|||||||処理結果です。 |
| error[]| <a href="./Error.md">Error</a>||||||| エラーの内容です。 |
| NegativeCampaignRetargetingListValues|||||||||
| negativeCampaignRetargetingList|<a href="./NegativeCampaignRetargetingList.md">NegativeCampaignRetargetingList</a>|1|0|○|-|-|-|get/mutateメソッドの実行結果です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
