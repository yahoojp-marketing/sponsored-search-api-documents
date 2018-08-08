# WebpageCondition
WebpageConditionオブジェクトは、Webpageの条件を保持します。
### Service
+ [AdGroupWebpageService](../../services/AdGroupWebpageService.md)

### Namespace
[AdGroupWebpageService#Namespace](../../services/AdGroupWebpageService.md#namespace)

| Field | Type | Description | response | add | set | remove
|---|---|---|---|---|---|---|
|type| enum [WebpageConditionType](./WebpageConditionType.md) | Webページの条件種別<br>※ALL_PAGESは広告グループに1つしか設定できない、<br>除外の場合は設定できない | yes | Req | Ignore | Ignore |
|argument| xsd:string | 条件の設定値(正規表現の指定可) | yes | Req<br>※typeがALL_PAGESの場合はOptional | Ignore | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
