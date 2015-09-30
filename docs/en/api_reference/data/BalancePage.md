# BalancePage
Account balance and a page of balance resulting from the query done by BalanceService.
### Service
+ [BalanceService](../services/BalanceService.md)

| Field | Data Type | Description | 
|---|---|---|
| Page(inherited)|||
| totalNumEntries| xsd:int| The total number of retrieved entries. |
| Page.Type| xsd:string| This field indicates the subtype of Page of this instance. |
| BalancePage|||
| values[]| <a href="./BalanceValues.md">BalanceValues</a>| List of balance. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
