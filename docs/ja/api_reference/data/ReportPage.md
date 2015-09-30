# ReportPage
ReportPageオブジェクトは、取得されるレポートのエントリーを表します。
### Service
+ [ReportService](../services/ReportService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| Page(inherited)|||
| totalNumEntries| xsd:int| 取得される項目の総件数です。 |
| Page.Type| xsd:string| このインスタンスのPageのサブタイプです。 |
| ReportPage|||
| values[]| <a href="./ReportValues.md">ReportValues</a>| ReportValuesオブジェクトの配列です。配列には、レポートの情報が含まれます。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
