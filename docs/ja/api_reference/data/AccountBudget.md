# AccountBudget
AccountBudgetオブジェクトは、広告予算を表します。
### Service
+ [AccountService](../services/AccountService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| amount| xsd:long| 広告の予算金額です。3000以上を指定する必要があります。 |
| limitChargeType| enum <a href="../data/LimitChargeType.md">LimitChargeType</a>| 月額など予算に関するアカウントの種別です。 |
| startDate| xsd:string| 掲載開始日です。当日以降を設定する必要があります。 |
| endDate| xsd:string| 掲載終了日です。掲載開始日以降を設定する必要があります。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
