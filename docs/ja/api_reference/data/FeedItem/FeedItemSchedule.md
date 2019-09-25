

# FeedItemSchedule

FeedItemScheduleオブジェクトは、広告表示オプションの配信スケジュール設定を表します。

### Service

+ [FeedItemService](../../services/FeedItemService.md)

### Namespace

[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| dayOfWeek | enum [DayOfWeek](./DayOfWeek.md) | 曜日です。 | yes | - | Requirement | Requirement | - | |
| startHour | xsd:long | 開始時です。<br/>※0 ～ 23の範囲で設定してください。 | yes | - | Requirement | Requirement | - | |
| startMinute | enum [MinuteOfHour](./MinuteOfHour.md) | 開始分です。 | yes | - | Requirement | Requirement | - | |
| endHour | xsd:long | 終了時です。<br/>※0 ～ 24の範囲で設定してください。 | yes | - | Requirement | Requirement | - | |
| endMinute | enum [MinuteOfHour](./MinuteOfHour.md) | 終了分です。<br/>※終了時が「24」で設定されている場合、「ZERO」のみ設定可能です。 | yes | - | Requirement | Requirement | - | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
