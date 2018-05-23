# BiddingStrategySelector
BiddingStrategySelectorオブジェクトは、自動入札設定の検索条件に関する情報を表します。
### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE |
|---|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| ─| ─| ─ |
| biddingStrategyIds[]| xsd:long| 自動入札IDです。| ─| ─| ─ |
| biddingStrategyTypes[]| enum <a href="BiddingStrategyType.md">BiddingStrategyType</a>| 自動入札タイプです。| ─| ─| ─ |
| paging| <a href="../Common/Paging.md"><br>Paging</a>| 取得範囲です。| ─| ─| ─ |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
