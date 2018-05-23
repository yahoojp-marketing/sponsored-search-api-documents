# SharedCriterion
SharedCriterion object holds negative keyword information.

### Service
+ [SharedCriterionService](../../services/SharedCriterionService.md)

### Namespace
[SharedCriterionService#Namespace](../../services/SharedCriterionService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|
| accountId | long | Account ID. | Req | - | - | - | - |
| sharedListId | long | Account shared list ID. | Req | - | Requirement | - | Requirement|
| criterionId | long | Criterion ID. | Req | - | - | - | Requirement |
| text | string | Keyword. | Req | - | Requirement | - | - | 
| matchType | enum<br> [KeywordMatchType](KeywordMatchType.md) | Keyword match type. |Req | - | Requirement | - | - |
| criterionUseType | enum<br> [SharedCriterionUse](SharedCriterionUse.md) | Keyword type. | Req | - | - | - | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
