# NegativeCampaignRetargetingListOperation
NegativeCampaignRetargetingListOperationは、mutateメソッドで操作対象のキャンペーンレベルでのターゲットリスト除外対象設定を保持するオブジェクトです。

### Service
+ [NegativeCampaignRetargetingListService](../services/NegativeCampaignRetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| Operation(inherited)|||||||||
| operator| enum <a href="./Operator.md">Operator</a>||||||| 処理を表す演算子です。 |
| RetargetingListOperation|||||||
| accountId| long| 1| 1| -| Req| -| Req| アカウントIDです。|
| Operand[]| <a href="./NegativeCampaignRetargetingList.md">NegativeCampaignRetargetingList</a>| unbounded| 1| -| Req| -| Req| 操作対象キャンペーン除外ユーザリストの情報です。|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
