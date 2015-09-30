# CampaignReturnValue
CampaignReturnValueオブジェクトは、キャンペーンの情報を含む操作結果として戻される値を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| ListReturnValue(inherited)|||
| <a href="./ListReturnValue.md">ListReturnValue.Type</a>| xsd:string| このインスタンスの ListReturnValue のサブタイプを示します。 |
| operation.Type| xsd:string| mutate処理の内容です。 |
| AccountReturnValue|||
| value[]| <a href="./CampaignValues.md">CampaignValues</a>| キャンペーンに関する情報です。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
