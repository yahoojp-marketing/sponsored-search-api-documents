# AdScheduleTarget
Ad schedule target.
### Service
+ [CampaignTargetService](../services/CampaignTargetService.md)

| Field | Data Type | Description | 
|---|---|---|
| type| enum <a href="../data/TargetType.md">TargetType</a>| Type of target.|
| dayOfWeek| enum <a href="../data/DayOfWeek.md">DayOfWeek</a>| Day of the week the schedule applies to.|
| startHour| xsd:int| Starting hour in 24 hour time (0-23). This field must be between 0.0 and 23.0, inclusive. |
| startMinute| enum <a href="../data/MinuteOfHour.md">MinuteOfHour</a>| Interval starts these minutes after the starting hour. This field is required and should not be null. |
| endHour| xsd:int| Ending hour in 24 hour time (0-24); 24 signifies end of the day. This field must be between 0.0 and 24.0, inclusively. |
| endMinute| enum <a href="../data/MinuteOfHour.md">MinuteOfHour</a>| Interval ends these minutes after the ending hour. This field is required and should not be null.|
| bidMultiplier| xsd:double| Multiplying factor for bids during this specified time interval.<br>You can specify the range from 0.10 to 10.0.<br>(The number of fractional digits after a decimal point is two that you can specify.) |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
