# TargetingKeyword
TargetingKeyword contains keyword setting for Data Auto Insertion.

### Service
+ [FeedItemService](../services/FeedItemService.md)

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
  <td>targetingKeywordId</td>
  <td>xsd:long</td>
  <td>ID to identify the Targeting keyword (text).<br>* To deactive, set "0".</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>text</td>
  <td>xsd:string</td>
  <td>Keyword text.<br>* Insert limit: Up to 80 characters and/or 10 words.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>matchType</td>
  <td>enum <a href="./KeywordMatchType.md">KeywordMatchType</a></td>
  <td>Match type.<br>To select what kind of matching to be made between the keywords and search query.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
