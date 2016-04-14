# MobileAd
Mobile ad excluding for Smartphone.<br>
* mutate(ADD) and mutate(SET) are unavailable due to the closing of mobile (feature phone) ads.<br>
　get and mutate(REMOVE) are still available to use.

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

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
  <td colspan="8"><a href="./Ad.md">Ad</a>(inherited)</td>
 </tr>
 <tr>
  <td>type</td>
  <td>enum <a href="./AdType.md">AdType</a></td>
  <td>Type of ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advancedUrl</td>
  <td>xsd:string</td>
  <td>Landing Page URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Requirement if not upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advancedMobileUrl</td>
  <td>xsd:string</td>
  <td>Landing Page URL (Smartphone).</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if not upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if not upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>Custome parameters.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if not upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advanced</td>
  <td>enum <a href="./Advanced.md">Advanced</a></td>
  <td>Flag of Adanced URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Default: TRUE</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>url</td>
  <td>xsd:string</td>
  <td>Destination URL before upgrading.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Ignore if not upgrading URL (advanced=TRUE).<br>*Requirement if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>Display URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br>*Ignore if type of ad is App ad.</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>headline</td>
  <td>xsd:string</td>
  <td>Title of ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>description</td>
  <td>xsd:string</td>
  <td>Description of ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td colspan="8">MobileAd</td>
 </tr>
 <tr>
  <td>markupLanguages</td>
  <td>enum <a href="./MarkupLanguageType.md">MarkupLanguageType</a></td>
  <td>List of markup languages to use for the mobile ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mobileCarriers</td>
  <td>enum <a href="./CarrierName.md">CarrierName</a></td>
  <td>Mobile carriers to display the mobile ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
