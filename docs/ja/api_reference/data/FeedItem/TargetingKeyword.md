

# TargetingKeyword

TargetingKeywordオブジェクトは、データ自動挿入のターゲットキーワードを表します。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| targetingKeywordId | xsd:long | 指定したキーワード（text）を識別する IDになります。<br/>※設定を解除する場合は「0」を指定 してください。 | yes | - | - | Optional | - | |
| text | xsd:string | 指定するキーワードです。<br/>※入力制限：80文字、10ワード までです。 | yes | - | Requirement | Requirement | - | |
| matchType | enum [KeywordMatchType](./KeywordMatchType.md) | マッチタイプです。<br/>入力されたキーワードが検索クエリに どのように一致するかを示します。 | yes | - | Requirement | Requirement | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
