# AdGroupAdSelector
AdGroupAdSelectorオブジェクトは、操作の対象とする広告およびフィルタ条件を表します。
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignIds[]| xsd:long| キャンペーンIDです。 |
| adGroupIds[]| xsd:long| 広告グループIDです。 |
| adIds[]| xsd:long| 広告IDです。<br>指定しない場合は、広告グループID以下のすべての広告が含まれます。 |
| adTypes[]| enum <a href="../data/AdType.md">AdType</a>| 広告種別です。 |
| userStatus[]| enum <a href="../data/UserStatus.md">UserStatus</a>| ユーザーにより設定される広告の掲載状況です。<br>指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。 |
| approvalStatuses[]| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| 審査状況です。 |
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
