

# MultipleFeedItemAttribute

MultipleFeedItemAttributeオブジェクトは、フィードアイテムの属性情報の値を格納します。
以下のplaceholderFieldの使用時に適用するオブジェクトです。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

### Inheritance

+ [FeedItemAttribute](./FeedItemAttribute.md)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| feedAttributeValues[] | [FeedAttributeValue](./FeedAttributeValue.md) | フィードアイテム情報の値です。<br/>※ADDITIONAL_ADVANCED_URLSおよびADDITIONAL_ADVANCED_MOBILE_URLS、STRUCTURED_SNIPPET_VALUESは、最大9件設定できます。<br>※STRUCTURED_SNIPPET_VALUESは3個以上設定する必要があります。 | yes | - | Requirement | Requirement<br/> | - | |
| isRemove | enum [IsRemove](./IsRemove.md) | フィードアイテムを削除します。<br/>※MultipleFeedAttributeValueを削除する場合は、isRemove=TRUEを指定します。 | - | - | - | Optional | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
