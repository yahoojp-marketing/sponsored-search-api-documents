# CampaignServingStatus (enum)
CampaignServingStatusは、キャンペーンレベルの配信状況です。
ユーザーによる広告配信の調整に関わらず、キャンペーンとしての状態を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| 値 | データ型 | 説明 | 
|---|---|---|
| SERVING| string| キャンペーンは、現在配信されています。 |
| ENDED| string| 配信が終了しています。<br>設定されたキャンペーン期間後のため、現在配信されていません。 |
| PENDING| string| 配信が開始していません。<br>設定されたキャンペーン期間前のため、現在まだ配信されていません。 |
| STOP| string| キャンペーンは、現在配信されていません。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
