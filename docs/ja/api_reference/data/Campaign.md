# Campaign
Campaignオブジェクトは、キャンペーンの情報を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId(notupdatable)| xsd:long| アカウントIDです。| Req| Req| Req |
| campaignId(notupdatable)| xsd:long| キャンペーンIDです。| ─| Req| Req |
| campaignName(notupdatable)| xsd:string| キャンペーン名です。| Req| Opt| ─ |
| userStatuses(updatable)| enum <a href="../data/UserStatus.md">UserStatus</a>| ユーザーにより広告配信の有無を調整できる設定です。| Req| Opt| ─ |
| servingStatus| enum <a href="../data/CampaignServingStatus.md">CampaignServingStatus</a>| キャンペーンレベルの配信状況です。<br>ユーザーによる広告配信の調整に関わらず、キャンペーンとしての状態を表します。| ─| ─| ─ |
| startDate(updatable)| xsd:string| キャンペーンの開始日です。過去の日付は指定できません。| Opt| Opt| ─ |
| endDate(updatable)| xsd:string| キャンペーンの終了日です。過去の日付、startDate以前の日付は指定できません。| Opt| Opt| ─ |
| budget(updatable)| <a href="../data/Budget.md">Budget</a>| キャンペーンの予算です。| Req| Opt| ─ |
| biddingStrategyConfiguration| <a href="../data/BiddingStrategy_Campaign.md">BiddingStrategy</a>| 入札設定です。※BudgetOptimizerの登録、更新は行えません。（照会のみ可能です）| Req| Opt| ─ |
| biddingStrategyFailedReason| enum <a href="../data/BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a>| 自動入札の設定に失敗した理由です。※失敗時のみレスポンスされます。| ─| ─| ─ |
| failedBiddingStrategyConfiguration| <a href="../data/BiddingStrategy_Campaign.md">BiddingStrategy</a>| 登録に失敗した自動入札設定です。※失敗時のみレスポンスされます。| ─| ─| ─ |
| conversionOptimizerEligibility| enum <a href="../data/ConversionOptimizerEligibility.md">ConversionOptimizerEligibility</a>| コンバージョンオプティマイザーが利用可能であるか判定します。| ─| ─| ─ |
| adServingOptimizationStatus(updatable)| enum <a href="../data/AdServingOptimizationStatus.md">AdServingOptimizationStatus</a>| 広告表示の最適化の設定です。| Opt| Opt| ─ |
| settings[](updatable)| <a href="./Settings.md">Settings</a><br><br>inherited <a href="./GeoTargetTypeSetting.md">GeoTargetTypeSetting</a><br><br>inherited <a href="./KeywordMatchSetting.md">KeywordMatchSetting</a>| 地域ターゲティングの設定です。| Opt| Opt| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
