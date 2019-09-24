

# RetargetingAccountStatus

RetargetingAccountStatusは、アカウントのリタゲ審査ステータスを保持するオブジェクトです。

### Service

+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace

[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Field | Type | Description | response | add | set |
| ----- | ---- | ----------- | -------- | --------- | --------- |
| agreeDate | xsd:string | 規約同意日です。<br/>※YYYYMMDD形式です。 | yes | - | - | |
| reviewStatus | enum [ReviewStatus](./ReviewStatus.md) | 審査状態です。<br/>初回審査はありません。 | yes | - | - | |
| reviewRequestDate | xsd:string | 再審査依頼日です。<br/>※YYYYMMDD形式です。 | yes | - | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
