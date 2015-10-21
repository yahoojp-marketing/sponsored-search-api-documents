# AdGroupRetargetingList
AdGroupRetargetingListは、広告グループレベルでのターゲットリスト設定を保持するオブジェクトです。

### Service
+ [AdGroupRetargetingListService](../services/AdGroupRetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| accountId| long| 1| 1| ○| Ignore| Ignore| Ignore| アカウントIDです。 |
| campaignId| long| 1| 1| ○| Req| Req| Req| キャンペーンIDです。 |
| campaignName| string| 1| 0| ○| Ignore| Ignore| Ignore| キャンペーン名です。 |
| adGroupId| long| 1| 1| ○| Req| Req| Req| キャンペーンIDです。 |
| adGroupName| string| 1| 0| ○| Ignore| Ignore| Ignore| キャンペーン名です。 |
| criterionTargetList| <a href="./CriterionTargetList.md">CriterionTargetList</a>| 1| 1| ○| Req| Req| Req| ターゲットリストです。 |
| excludedType|enum <a href="./ExcludedType_AdGroupRetargetingList.md">ExcludedType</a>| 1| 0| ○| Opt| Opt| Req| 包含/追加設定です。<br>※Default値：INCLUDED |
| bidMultiplier| double| 1| 0| ○| Opt| Opt| Ignore| MaxCPC上昇値です。<br>※Default値：1.00 |
| targetAll| enum <a href="./TargetAll.md">TargetAll</a>| 1|0| ○| Opt| Opt| Ignore| 全ユーザの配信対象設定です。<br>※Default値：DEACTIVE |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
