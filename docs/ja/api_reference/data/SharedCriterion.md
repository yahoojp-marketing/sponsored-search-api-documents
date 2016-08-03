# SharedCriterion
SharedCriterionオブジェクトは、対象外キーワード情報を保持します。

### Service
+ [SharedCriterionService](../services/SharedCriterionService.md)

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|
| accountId | xsd:long | アカウントIDです。 | ○ | - | - | - | - |
| sharedListId | xsd:long | アカウント共有リストIDです。 | ○ | - | Requirement | - | Requirement|
| criterionId | xsd:long | クライテリオンIDです。 | ○ | - | - | - | Requirement |
| text | xsd:string | キーワードです。 | ○ | - | Requirement | - | - | 
| matchType | enum<br> [KeywordMatchType](../data/KeywordMatchType.md) | キーワードのマッチタイプです。 | ○ | - | Requirement | - | - |
| criterionUseType | enum<br> [SharedCriterionUse](../data/SharedCriterionUse.md) | キーワードの種別です。 | ○ | - | - | - | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
