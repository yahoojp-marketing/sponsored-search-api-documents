# ScheduleTarget
ScheduleTarget describes Day of week/Hour targeting report.
### Service
+ [CampaignTargetService](../../services/CampaignTargetService.md)

### Namespace
[CampaignTargetService#Namespace](../../services/CampaignTargetService.md#namespace)

| Field | Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Target (inherited)||||||
| targetId| xsd:string| Target ID| -| Req| Req |
| type| enum <a href="TargetType.md">TargetType</a>| Target Type| Req| Req| Req |
| ScheduleTarget||||||
| dayOfWeek| enum <a href="DayOfWeek.md">DayOfWeek</a>| Day of week| Req| —| — |
| startHour| xsd:int| Starting hour in 24 hour time.| Req| —| — |
| startMinute| enum <a href="MinuteOfHour.md">MinuteOfHour</a>| Interval starts these minutes after the starting hour.| Req| —| — |
| endHour| xsd:int| Ending hour in 24 hour time.| Req| —| — |
| endMinute| enum <a href="MinuteOfHour.md">MinuteOfHour</a>| Interval ends these minutes after the ending hour.| Req| —| — |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
