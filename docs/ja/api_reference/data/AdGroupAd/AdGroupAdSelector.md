

# AdGroupAdSelector

AdGroupAdSelectorオブジェクトは、操作の対象とする広告およびフィルタ条件を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | 検索条件：アカウントID | - | Requirement | - | - | - | |
| campaignIds[0...1000] | xsd:long | 検索条件：キャンペーンID | - | Optional | - | - | - | |
| adGroupIds[0...1000] | xsd:long | 検索条件：広告グループID | - | Optional | - | - | - | |
| adIds[0...1000] | xsd:long | 検索条件：広告ID | - | Optional | - | - | - | |
| adTypes[0...4] | enum [AdType](./AdType.md) | 検索条件：広告の種類 | - | Optional | - | - | - | |
| userStatuses[0...2] | enum [UserStatus](./UserStatus.md) | 検索条件：ユーザーにより設定される広告の掲載状況<br/>※指定しない 場合は、フィルタ条件にすべての掲載状況が含まれます。 | - | Optional | - | - | - | |
| approvalStatuses[0...5] | enum [ApprovalStatus](./ApprovalStatus.md) | 検索条件：審査状況 | - | Optional | - | - | - | |
| labelIds[0...1000] | xsd:long | 検索条件：ラベルID | - | Optional | - | - | - | |
| containsLabelId | enum [ContainsLabelId](./ContainsLabelId.md) | 検索条件：ラベル情報取得フラグ | - | Optional | - | - | - | |
| paging | [Paging](../Common/Paging.md) | 検索条件：取得範囲 | - | Optional | - | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
