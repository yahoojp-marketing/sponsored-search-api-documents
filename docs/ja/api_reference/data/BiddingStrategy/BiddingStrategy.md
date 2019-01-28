# BiddingStrategy
BiddingStrategyオブジェクトは、入札方法を表します。
### Service
+ [BiddingStrategyService](../../services/BiddingStrategyService.md)

### Namespace
[BiddingStrategyService#Namespace](../../services/BiddingStrategyService.md#namespace)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE |
|---|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req| Req<br>                        (notupdatable)| Req<br>                        (notupdatable) |
| biddingStrategyId| xsd:long| 自動入札IDです。| ─| Req<br>                        (notupdatable)| Req<br>                        (notupdatable) |
| biddingStrategyName| xsd:string| 自動入札名です。（50文字以内になります）| Req| Opt<br>                        (updatable)| ─ |
| biddingStrategyType| enum <a href="BiddingStrategyType.md">BiddingStrategyType</a>| 自動入札タイプです。| ─| ─| ─ |
| biddingScheme| <a href="BiddingScheme.md">BiddingScheme</a><br><br> inherited <a href="PageOnePromotedBiddingScheme.md">PageOnePromotedBiddingScheme </a><br><br> inherited <a href="TargetCpaBiddingScheme.md">TargetCpaBiddingScheme</a><br><br> inherited <a href="TargetSpendBiddingScheme.md">TargetSpendBiddingScheme</a><br><br> inherited <a href="TargetRoasBiddingScheme.md">TargetRoasBiddingScheme</a>| 自動入札設定詳細です。| Req| Opt<br>                        (updatable)| ─ |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
