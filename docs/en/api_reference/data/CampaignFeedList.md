# CampaignFeedList
CampaignFeedList object describes FeedItem information connected to campaign.
### Service
+ [CampaignFeedService](../services/CampaignFeedService.md)

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
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>placeholderType</td>
  <td>enum <a href="./CampaignFeedPlaceholderType.md">CampaignFeedPlaceholderType</a></td>
  <td>FeedItem Information type.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignFeed[1..20]</td>
  <td><a href="./CampaignFeed.md">CampaignFeed</a></td>
  <td>The container of FeedItem information.<br>If SET 0 case, all CampaignFeed will be deleted.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>devicePlatform </td>
  <td>enum <a href="./DevicePlatform.md">DevicePlatform</a></td>
  <td>Specifies device.<br>*If specify CALLEXTENSIONS for placeholderType, this field can be skipped. </td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
