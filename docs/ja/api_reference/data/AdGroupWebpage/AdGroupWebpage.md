# AdGroupWebpage
AdGroupWebpageオブジェクトは、広告グループに関連付けた配信/除外設定の情報を保持します
### Service
+ [AdGroupWebpageService](../../services/AdGroupWebpageService.md)

### Namespace
[AdGroupWebpageService#Namespace](../../services/AdGroupWebpageService.md#namespace)

| Field | Type | Description | response | add | set | remove
|---|---|---|---|---|---|---|
| accountId | xsd:long | アカウントID | yes | Ignore | Ignore | Ignore |
| campaignId | xsd:long | キャンペーンID | yes | Req | Req | Req |
| campaignTrackId | xsd:long | キャンペーントラッキングID	| yes | Ignore | Ignore | Ignore |
| adGroupId | xsd:long | 広告グループID | yes | Req | Req | Req |
| adGroupTrackId | xsd:long | 広告グループトラッキングID | yes | Ignore | Ignore | Ignore |
| userStatus | enum [UserStatus](./UserStatus.md) | 配信ステータス | yes | Optional | Optional<br>※ExcludedTypeがINCLUDEDのみ更新可 | Ignore |
| excludedType | enum [ExcludedType](./ExcludedType.md) | 配信/除外設定 | yes | Optional<br>Default : INCLUDED | Ignore | Ignore |
| webpage | [Webpage](./Webpage.md) | Webpage情報 | yes | Req | Req | Req |
| bid | [Bid](./Bid.md) | 入札価格 | yes | Optional | Optional<br>※ExcludedTypeがINCLUDEDのみ更新可 | Ignore |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
