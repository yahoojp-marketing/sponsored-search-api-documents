

# FeedItemAttribute

FeedItemAttributeオブジェクトは、フィードアイテムの属性情報の値を格納します。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| placeholderField | enum [FeedItemPlaceholderField](./FeedItemPlaceholderField.md) | フィードアイテム情報の種類です。 | yes | - | Requirement<br/>※アドカスタマイザーの場合、Ignore | Requirement<br/>※アドカスタマイザーの場合、Ignore | Ignore | |
| feedAttributeId | xsd:long | フィード属性IDです。 | yes | - | Ignore<br/>※アドカスタマイザーの場合、Requirement | Ignore<br/>※アドカスタマイザーの場合、Requirement | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
