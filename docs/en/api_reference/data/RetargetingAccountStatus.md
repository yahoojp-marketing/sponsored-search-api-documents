# RetargetingAccountStatus
RetargetingAccountStatus is an object that holds retargeting review status of account.

### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| field | type | max<br>Occurs | min<br>Occurs | resp<br>onse | add | set | remove | description | 
|---|---|---|---|---|---|---|---|---|
| agreeDate| string| 1| 0| ○| Ignore| Ignore| -| Agreement date.<br>*In yyyyMMdd format|
| reviewStatus| enum <a href="./ReviewStatus.md">ReviewStatus</a>| 1| 0| ○| Ignore| Ignore| -| Review status.<br>It will not display on initial review. |
| reviewRequestDate| string| 1| 0| ○| Ignore| Ignore| -| Re-examination review request date.<br>*In yyyyMMdd format|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>

