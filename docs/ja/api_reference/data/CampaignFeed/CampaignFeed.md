# CampaignFeed
CampaignFeedオブジェクトは、キャンペーンに紐づけられたFeedItem情報を表します。
### Service
+ [CampaignFeedService](../../services/CampaignFeedService.md)

### Namespace
[CampaignFeedService#Namespace](../../services/CampaignFeedService.md#namespace)

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
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>feedItemId</td>
  <td>xsd:long</td>
  <td>FeedItem情報のIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>Updatable</td>
  <td>-</td>
 </tr>
  <tr>
  <td>placeholderType</td>
  <td>enum <a href="CampaignFeedPlaceholderType.md">CampaignFeedPlaceholderType</a></td>
  <td>FeedItem情報の種類です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Ignore</td>
  <td>-</td>
 </tr>
<table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
