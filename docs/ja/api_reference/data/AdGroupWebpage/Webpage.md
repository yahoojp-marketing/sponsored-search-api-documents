# Webpage
Webpageオブジェクトは、配信/除外設定するWebpageの条件を保持します。
### Service
+ [AdGroupWebpageService](../../services/AdGroupWebpageService.md)

### Namespace
[AdGroupWebpageService#Namespace](../../services/AdGroupWebpageService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|
| targetId| xsd:long| Webpageを識別するID | yes | Ignore | Ignore | Req | Req |
| targetTrackId| xsd:long| Webpageを識別するトラッキングID | yes | Ignore | Ignore | Ignore | Ignore |
| parameter | enum <a href="WebpageParameter.md">WebpageParameter</a>| 配信/除外設定の条件 | yes | Ignore | Req | Ignore | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
