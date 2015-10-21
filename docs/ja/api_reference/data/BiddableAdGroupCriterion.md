# BiddableAdGroupCriterion
BiddableAdGroupCriterionオブジェクトは、広告グループの単価設定可能（包含）クライテリアです。
### ServiceInheritance
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [BiddableAdGroupCriterion](../services/BiddableAdGroupCriterion.md)
+ [AdGroupCriterion](../services/AdGroupCriterion.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| AdGroupCriterion(inherited)||||||
| accountId(notupdatable)| xsd:long| アカウントIDです。| Req| Req| Req |
| campaignId(notupdatable)| xsd:long| キャンペーンIDです。| Req| Req| Req |
| campaignName(notupdatable)| xsd:string| キャンペーン名です。| ─| ─| ─ |
| adGroupId(notupdatable)| xsd:long| 広告グループIDです。| Req| Req| Req |
| adGroupName(notupdatable)| xsd:string| 広告グループ名です。| ─| ─| ─ |
| criterionUse| enum <a href="./CriterionUse.md">CriterionUse</a>| クライテリアを単価設定可能にするか除外にするかを選択します。| Req| ─| ─ |
| criterion(updatable)| <a href="./Criterion.md">Criterion</a>inherited <a href="./Keyword.md">Keyword</a>| クライテリアです。| Req| Req| Req |
| BiddableAdGroupCriterion||||||
| userStatus(updatable)| enum <a href="./UserStatus.md">UserStatus</a>| ユーザーにより設定される広告の掲載状況です。指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。| Req| Opt| ─ |
| approvalStatus| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| 審査状況です。| ─| ─| ─ |
| disapprovalReasonCodes| xsd:string| 審査否認コードです。<br>各コードのその内容は、<a href="../appendix/ed_reasons.md"><span>Editorial Reason Text</span></a>をご確認ください。| ─| ─| ─ |
| destinationUrl(updatable)| xsd:string| リンク先URLです。|Opt<br>※Androidのアプリダウンロード<br>キャンペーン：Ignore| Opt| ─ |
| biddingStrategyConfiguration| <a href="../data/BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a>| 入札設定です。<br>※現在有効な入札設定がレスポンスされます。<br>※親エンティティの有効な入札設定が適用されます。| Req| Opt<br>                    (updatable)| ─ |
| biddingStrategyFailedReason| enum <a href="../data/BiddingStrategyFailedReason.md">BiddingStrategyFailedReason</a>| 自動入札設定に失敗した理由です。<br>※失敗時のみレスポンスされます。| ─| ─| ─ |
| failedBiddingStrategyConfiguration| <a href="../data/BiddingStrategy_AdGroupCriterion.md">BiddingStrategy</a>| 登録に失敗した自動入札設定です。<br>※失敗時のみレスポンスされます。| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
