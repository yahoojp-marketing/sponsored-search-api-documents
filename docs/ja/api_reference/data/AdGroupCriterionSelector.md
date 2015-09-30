# AdGroupCriterionSelector
AdGroupCriterionSelectorオブジェクトは、操作の対象となる広告グループのクライテリアを表します。
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd: long| アカウントIDです。 |
| campaignIds[]| xsd: long| キャンペーンIDの配列です。 |
| adGroupIds[]| xsd: long| 広告グループIDの配列です。 |
| criterionIds[]| xsd: long| クライテリオンIDの配列です。指定しない場合は、広告グループID以下のすべてのクライテリアが含まれます。 |
| criterionUse| enum <a href="../data/CriterionUse.md">CriterionUse</a>| クライテリアを単価設定可能にするか除外にするかを選択します。 |
| userStatuses[]| enum <a href="../data/UserStatus.md">UserStatus</a>| ユーザーにより設定される広告の掲載状況です。指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。 |
| biddingStrategyIds[]| xsd:long| 自動入札IDです。 |
| approvalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| 審査状況です。 |
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
