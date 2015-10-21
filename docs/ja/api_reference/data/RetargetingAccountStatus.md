# RetargetingAccountStatus
RetargetingAccountStatusは、アカウントのリタゲ審査ステータスを保持するオブジェクトです。

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| agreeDate| string| 1| 0| ○| Ignore| Ignore| -| 規約同意日です。<br>※yyyyMMdd形式 |
| reviewStatus| enum <a href="./ReviewStatus.md">ReviewStatus</a>| 1| 0| ○| Ignore| Ignore| -| 審査状態です。<br>初回審査はありません。 |
| reviewRequestDate| string| 1| 0| ○| Ignore| Ignore| -| 再審査依頼日です。<br>※yyyyMMdd形式 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

