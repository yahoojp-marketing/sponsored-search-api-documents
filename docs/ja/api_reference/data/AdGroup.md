# AdGroup
AdGroup オブジェクトは、広告グループを表します。
### Service
+ [AdGroupService](../services/AdGroupService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountid(notupdatable)| xsd:long| アカウントIDです。| Req| Req| Req |
| campaignid(notupdatable)| xsd:long| キャンペーンIDです。| Req| Req| Req |
| campaignName(notupdatable)| xsd:string| キャンペーン名です。| ─| ─| ─ |
| adGroupId(notupdatable)| xsd:long| 広告グループIDです。| ─| Req| Req |
| adGroupName(updatable)| xsd:string| 広告グループ名です。| Req| Opt| ─ |
| userStatus(updatable)| enum <a href="../data/UserStatus.md">UserStatus</a>| ユーザーにより設定される掲載状況です。| Req| Opt| Req |
| biddingStrategyConfiguration| <a href="../data/BiddingStrategy_AdGroup.md">BiddingStrategy</a>| 入札設定です。<br>※現在有効な入札設定がレスポンスされます。<br>※BudgetOptimizerの登録、更新は行えません。（照会のみ可能）<br>※広告グループ単位で入札設定を行わない場合は、biddingStrategyTypeに「NONE」を登録します。<br>※入札設定を行わない場合は、デフォルトで親エンティティの入札設定が適用されます。| Opt| Opt(updatable)| ─ |
| biddingStrategyFailedReason| enum <a href="../data/BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a>| 自動入札の設定に失敗した理由です。<br>※失敗時のみレスポンスされます。| ─| ─| ─ |
| failedBiddingStrategyConfiguration| <a href="../data/BiddingStrategy_AdGroup.md">BiddingStrategy</a>| 登録に失敗した自動入札設定<br>※失敗時のみレスポンスされます。| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
