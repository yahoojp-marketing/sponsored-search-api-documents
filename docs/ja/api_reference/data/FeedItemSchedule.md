# FeedItemSchedule
FeedItemScheduleオブジェクトは、広告表示オプションの配信スケジュール設定を表します。
### Service
+ [FeedItemService](../services/FeedItemService.md)

| フィールド | データ型 | 説明 | SET | 
|---|---|---|---|
| dayOfWeek| enum <a href="./DayOfWeek.md">DayOfWeek</a>| 曜日です。<br>規定値を指定してください。| Req |
| startHour| xsd:long| 開始時です。<br>0?23の範囲で設定してください。| Req |
| startMinute| enum <a href="./MinuteOfHour.md">MinuteOfHour</a>| 開始分です。<br>規定値で指定してください。| Req |
| endHour| xsd:long| 終了時です。<br>0?24の範囲で設定してください。| Req |
| endMinute| enum <a href="./MinuteOfHour.md">MinuteOfHour</a>| 終了分です。<br>規定値で指定してください。<br>endHourが24で設定されている場合、endMinuteは、ZEROのみが設定可能です。| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
