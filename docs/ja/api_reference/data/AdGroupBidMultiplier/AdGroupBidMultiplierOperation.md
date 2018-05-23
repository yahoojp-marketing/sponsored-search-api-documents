# AdGroupBidMultiplierOperation
AdGroupBidMultiplierOperationオブジェクトは、入札価格調整率の操作内容を表します。
### Service
+ [AdGroupBidMultiplierService](../../services/AdGroupBidMultiplierService.md)

### Namespace
[AdGroupBidMultiplierService#Namespace](../../services/AdGroupBidMultiplierService.md#namespace)

### Inheritance
+ Operation

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|
| Operation(inherited)||||||||
| operator| enum Operator| SET、REMOVEが指定可能です。||||||
| AdGroupBidMultiplierOperation||||||||
| accountId| xsd:long| アカウントIDです。| - | - | - | Requirement | Requirement |
| operand[1..10000]| <a href="AdGroupBidMultiplier.md">AdGroupBidMultiplier</a>| 操作の対象を表します。 | - | - | - | Requirement | Requirement |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
