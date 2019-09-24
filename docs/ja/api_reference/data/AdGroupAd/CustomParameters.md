

# CustomParameters

CustomParametersオブジェクトは、カスタムパラメータの設定を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| isRemove | enum [IsRemove](./IsRemove.md) | 削除フラグです。 | yes | - | - | Optional<br/>※AdGroupAdServiceの場合、Ignore。 | - | |
| parameters[0...3] | [CustomParameter](./CustomParameter.md) | パラメータです。<br/> | yes | - | Requirement | Ignore | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
