

# FeedItemSchedule

FeedItemSchedule object describes display schedule from Ad Display Option.

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| dayOfWeek | enum [DayOfWeek](./DayOfWeek.md) | Day of week | yes | - | Requirement | Requirement | - | |
| startHour | xsd:long | Start time in hour.<br/>*Specify from 0 - 23. | yes | - | Requirement | Requirement | - | |
| startMinute | enum [MinuteOfHour](./MinuteOfHour.md) | Start time in minute. | yes | - | Requirement | Requirement | - | |
| endHour | xsd:long | End time in hour.<br/>*Specify from 0 - 24. | yes | - | Requirement | Requirement | - | |
| endMinute | enum [MinuteOfHour](./MinuteOfHour.md) | End time in minute.<br/>* If end time in hour is set &#34;24&#34;, can set only &#34;ZERO&#34;. | yes | - | Requirement | Requirement | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
