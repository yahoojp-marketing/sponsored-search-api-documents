# AdGroupOperation
AdGroupOperationオブジェクトは、操作の対象となる広告グループと処理の内容を表します。
### Service
+ [AdGroupService](../services/AdGroupService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Operation(inherited)||||||
| operator| enum <a href="./Operator.md">Operator</a>| 処理を表す演算子です。| Req| Req| Req |
| AdGroupOperation||||||
| accountId| xsd:long| アカウントIDです。| Req| Req| Req |
| campaignId| xsd:long| キャンペーンIDです。| Req| Req| Req |
| operand[]| <a href="./AdGroup.md">AdGroup</a>| AdGroupオブジェクトの配列です。各配列には処理の対象となる広告グループの情報が含まれます。| Req| Req| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
