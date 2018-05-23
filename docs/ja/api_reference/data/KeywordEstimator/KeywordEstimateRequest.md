# KeywordEstimateRequest
keywordEstimateRequestオブジェクトは、見積もりを行うキーワードを格納するコンテナです。
### Service
+ [KeywordEstimatorService](../../services/KeywordEstimatorService.md)

### Namespace
[KeywordEstimatorService#Namespace](../../services/KeywordEstimatorService.md#namespace)

| フィールド | 必須 | データ型 | 説明 |
|---|---|---|---|
| Keyword| ○| <a href="EstimateKeyword.md">EstimateKeyword</a>| 見積もりを行うキーワードのコンテナです。 |
| isNegative| | <a href="IsNegativeBool.md">IsNegativeBool</a>| 除外フラグ（TRUE, FALSE） |
| maxCpc| | xsd:long| キーワードの見積もりに使用する上限クリック単価です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
