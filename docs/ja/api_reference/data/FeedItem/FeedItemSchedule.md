# FeedItemSchedule
FeedItemScheduleオブジェクトは、広告表示オプションの配信スケジュール設定を表します。

### Service
+ [FeedItemService](../../services/FeedItemService.md)

### Namespace
[FeedItemService#Namespace](../../services/FeedItemService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>dayOfWeek</td>
  <td>enum <a href="DayOfWeek.md">DayOfWeek</a></td>
  <td>曜日です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startHour</td>
  <td>xsd:long</td>
  <td>開始時です。<br>※0 ～ 23の範囲で設定してください。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>startMinute</td>
  <td>enum <a href="MinuteOfHour.md">MinuteOfHour</a></td>
  <td>開始分です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endHour</td>
  <td>xsd:long</td>
  <td>終了時です。<br>※0 ～ 24の範囲で設定してください。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>endMinute</td>
  <td>enum <a href="MinuteOfHour.md">MinuteOfHour</a></td>
  <td>終了分です。<br>※終了時が「24」で設定されている場合、「ZERO」のみ設定可能です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
