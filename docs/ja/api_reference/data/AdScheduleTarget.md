# AdScheduleTarget
AdScheduleTargetオブジェクトは、スケジュール設定を表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | SET | 
|---|---|---|---|
| type| enum<a href="../data/TargetType.md">TargetType</a>| ターゲティング設定です。| Req |
| dayOfWeek(updatable)| enum<a href="../data/DayOfWeek.md">DayOfWeek</a>| 曜日です。| Req |
| startHour(updatable)| xsd:int| 24 時間表示の開始時刻です。| Req |
| startMinute(updatable)| enum<a href="../data/MinuteOfHour.md">MinuteOfHour</a>| 開始時刻の何分後に開始するかを示します。| Req |
| endHour(updatable)| xsd:int| 24 時間表示の終了時刻です。| Req |
| endMinute(updatable)| enum<a href="../data/MinuteOfHour.md">MinuteOfHour</a>| 終了時刻の何分後に終了するかを示します。| Req |
| bidMultiplier(updatable)| xsd:double| 指定期間の単価調整比率です。0.10?10.0の範囲で指定できます。（小数点2桁まで指定可能）| Opt |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
