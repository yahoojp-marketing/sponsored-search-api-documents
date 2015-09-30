# FeedItemSchedule
FeedItemSchedule object describes display schedule from Ad Display Option.
### Service
+ [FeedItemService](../services/FeedItemService.md)

| Field | Data Type | Description | SET | 
|---|---|---|---|
| dayOfWeek| enum <a href="./DayOfWeek.md">DayOfWeek</a>| Day of weekAssign specified value.| Req |
| startHour| xsd:long| Start hourSpecify the range from 0 to 23.| Req |
| startMinute| enum <a href="./MinuteOfHour.md">MinuteOfHour</a>| Start minuteAssign specified value.| Req |
| endHour| xsd:long| End hourSpecify the range from 0 to 24.| Req |
| endMinute| enum <a href="./MinuteOfHour.md">MinuteOfHour</a>| End minuteIf endHour has set by 24, only ZERO is assignable in endMinute.| Req |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
