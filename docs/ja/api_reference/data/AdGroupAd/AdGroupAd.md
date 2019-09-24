

# AdGroupAd

AdGroupAdオブジェクトは、広告に関する操作を行うための情報を表します。

### Service

+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace

[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントID | yes | - | Ignore | Ignore | Ignore | |
| campaignId | xsd:long | キャンペーンID | yes | - | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | |
| campaignTrackId | xsd:long | トラッキング用キャンペーンID<br/>※Sandbox環境では常に0が返ります。 | yes | - | Ignore | Ignore | Ignore | |
| campaignName | xsd:string | キャンペーン名 | yes | - | Ignore | Ignore | Ignore | |
| adGroupId | xsd:long | 広告グループID | yes | - | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | |
| adGroupTrackId | xsd:long | トラッキング用広告グループID<br/>※Sandbox環境では常に0が返ります。 | yes | - | Ignore | Ignore | Ignore | |
| adGroupName | xsd:string | 広告グループ名 | yes | - | Ignore | Ignore | Ignore | |
| adId | xsd:long | 広告ID | yes | - | Ignore | Requirement<br/><i>NotUpdatable</i> | Requirement<br/><i>NotUpdatable</i> | |
| adTrackId | xsd:long | トラッキング用広告ID<br/>※Sandbox環境では常に0が返ります。 | yes | - | Ignore | Ignore | Ignore | |
| adName | xsd:string | 広告名 | yes | - | Requirement | Optional<br/><i>Updatable</i> | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | ユーザーにより設定される掲載状況 | yes | - | Requirement | Optional<br/><i>Updatable</i> | Ignore | |
| trademarkStatus | enum [TrademarkStatus](./TrademarkStatus.md) | 商標保護ステータス | yes | - | Ignore | Ignore | Ignore | |
| invalidedTrademarks[0...n] | xsd:string | 制限された商標 | yes | - | Ignore | Ignore | Ignore | |
| approvalStatus | enum [ApprovalStatus](./ApprovalStatus.md) | 審査のステータス | yes | - | Ignore | Ignore | Ignore | |
| disapprovalReasonCodes | xsd:string | 審査否認の理由コード | yes | - | Ignore | Ignore | Ignore | |
| ad | [Ad](./Ad.md)<br>inherited [TextAd2](./TextAd2.md)<br>inherited [AppAd](./AppAd.md)<br>inherited [ExtendedTextAd](./ExtendedTextAd.md)<br>inherited [DynamicSearchLinkedAd](./DynamicSearchLinkedAd.md) | クリエイティブ広告の情報 | yes | - | Requirement | Ignore | Ignore | |
| feedFolderId | xsd:long | フィードフォルダID | yes | - | Ignore | Ignore | Ignore | |
| labels[0..50] | [Label](./Label.md) | ラベル | yes | Ignore | Ignore | Ignore | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
