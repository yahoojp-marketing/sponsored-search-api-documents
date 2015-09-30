# BidLandscapeValues
BidLandscapeValuesオブジェクトは、予測処理の結果を格納するコンテナです。
### Service
+ [BidLandscapeService](../services/BidLandscapeService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| ReturnValue(inherited)|||
| operationSucceeded| xsd:boolean| 処理結果です。 |
| error[]| <a href="./Error.md">Error</a>| エラーの内容です。 |
| BidLandscapeValues|||
| data[]| <a href="./BidLandscape.md">BidLandscape</a><br>inherited <a href="./AdGroupBidLandscape.md">AdGroupBidLandscape</a><br>inherited <a href="./CriterionBidLandscape.md">CriterionBidLandscape</a>| 広告グループ、またはクライテリアに関する予測の結果を返します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
