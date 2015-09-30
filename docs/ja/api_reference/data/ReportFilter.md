# ReportFilter
ReportFilterオブジェクトは、レポートのフィルタ条件を表します。フィルタ条件は最大5つまで設定が可能です。
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| field| xsd:string| フィルタ条件を設定するカラムです。 |
| operator| enum <a href="../data/ReportOperator.md">ReportOperator</a>| フィルタ条件を表す演算子です。 |
| values| xsd:string| fieldの条件値です。複数する場合は、カンマ区切り（,）で指定します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
