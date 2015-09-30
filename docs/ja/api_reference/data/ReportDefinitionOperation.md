# ReportDefinitionOperation
ReportDefinitionOperationオブジェクトは、操作の対象となるレポート定義および操作の内容を表します。
### Service
+ [ReportDefinitionService](../services/ReportDefinitionService.md)

| フィールド | データ型 | 説明 | 制限 | 
|---|---|---|---|
| Operation(inherited)||||
| operator| enum <a href="./Operator.md">Operator</a>| 処理を表す演算子です。| Req |
| ReportDefinitionOperation||||
| accountId| xsd:long| アカウントIDです。| Req |
| operand[]| <a href="./ReportDefinition.md">ReportDefinition</a>| ReportDefinitionオブジェクトの配列です。各配列にはレポートの定義が含まれます。| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
