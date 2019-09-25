

# CustomParameters

CustomParametersオブジェクトは、カスタムパラメータの設定を表します。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| isRemove | enum [IsRemove](./IsRemove.md) | 削除フラグです。 | yes | - | - | Optional | - | |
| parameters[0...3] | [CustomParameter](./CustomParameter.md) | パラメータです。<br/> | yes | - | Requirement | Requirement<br/>※既存の項目を置き換えます。<br/>※削除フラグを立てた（isRemove=TRUE）場合、Ignore。こちらの項目関係なく 全項目が削除されます。 | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
