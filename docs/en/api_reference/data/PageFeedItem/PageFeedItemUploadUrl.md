# PageFeedItemUploadUrl

PageFeedItemUploadUrl object displays content of process for get upload URL.

## Service

- [PageFeedItemService](../../services/PageFeedItemService.md)

## Namespace

[PageFeedItemService#Namespace](../../services/PageFeedItemService.md#namespace)

| Field        | Type                                                       | response | getUploadUrl | Description             |
|--------------|------------------------------------------------------------|----------|--------------|----------------|
| accountId    | xsd:long                                                   | ○        | Ignore       | Account       |
| uploadType   | enum [PageFeedItemUploadType](./PageFeedItemUploadType.md) | ○        | Requirement  | Kind of update method |
| feedFolderId | xsd:long                                                   | ○        | Requirement  | Feed folder ID  |
| url          | xsd:string                                                 | ○        | Ignore       | Upload URL   |

[![クリエイティブ・コモンズ・ライセンス](https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png)](http://creativecommons.org/licenses/by-nd/2.1/jp/)<br>
この 作品 は [クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。](http://creativecommons.org/licenses/by-nd/2.1/jp/)
