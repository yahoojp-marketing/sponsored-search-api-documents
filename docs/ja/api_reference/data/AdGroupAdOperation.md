# AdGroupAdOperation
AdGroupAdOperationオブジェクトは、操作の対象となる広告および操作の内容を表します。
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| 処理を表す演算子です。| Req |
| AdGroupAdOperation||||
| accountId| xsd:long| アカウントIDです。| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req |
| adGroupId| xsd:long| 広告グループIDです。| Req |
| operand[]| <a href="./AdGroupAd.md">AdGroupAd</a>| 操作を行う対象の広告です。| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
