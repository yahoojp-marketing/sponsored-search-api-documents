# ScheduleTarget
ScheduleTargetオブジェクトは、曜日・時間帯ターゲティングレポートを表します。
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Target (inherited)||||||
| targetId| xsd:string| ターゲットIDです。| -| Req| Req |
| type| enum <a href="../data/TargetType.md">TargetType</a>| ターゲットTypeです。| Req| Req| Req |
| ScheduleTarget||||||
| dayOfWeek| enum <a href="../data/DayOfWeek.md">DayOfWeek</a>| 曜日です。| Req| -| - |
| startHour| xsd:int| 24時間表示の開始時刻です。| Req| -| - |
| startMinute| enum <a href="./MinuteOfHour.md">MinuteOfHour</a>| 開始時刻の何分後に開始するかを示します。| Req| -| - |
| endHour| xsd:int| 24時間表示の終了時刻です。| Req| -| - |
| endMinute| enum <a href="./MinuteOfHour.md">MinuteOfHour</a>| 終了時刻の何分後に終了するかを示します。| Req| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
