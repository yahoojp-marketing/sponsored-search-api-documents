# ReviewStatus (enum)
ReviewStatusは、ターゲットリストの審査状態を表します。

### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

| Enumeration | Type | Description |
|---|---|---|
| APPROVED| string| 利用可能です。<br>※初回作成時のデフォルト設定です。|
| DISAPPROVED| string| 利用不可です。<br>プライバシーポリシーの違反などで強制停止されている状態です。|
| DISAPPROVED_WITH_REVIEW| string| 審査中です。<br>審査上問題なければ、一度利用不可になった ターゲットリストを利用可能に戻ります。|

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
