# BidLandscapeSelector
BidLandscapeSelectorオブジェクトは、予測するクライテリアを表します。
### Service
+ [BidLandscapeService](../services/BidLandscapeService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignId| xsd:long| キャンペーンIDです。 |
| adgroupId| xsd:long| 広告グループIDです。 |
| criterionIds| xsd:long| クライテリアIDです。最大100個まで指定できます。 |
| simType|enum <a href="../data/SimType.md">SimType</a> | 見積もりのタイプを指定します。 |
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
