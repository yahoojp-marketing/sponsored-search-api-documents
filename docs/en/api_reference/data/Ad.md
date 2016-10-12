# Ad
Ad object describes ad information.

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
  <td>Optional<br>*Requirement if upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
<tr>
  <td>additionalAdvancedUrls[0..9]</td>
  <td><a href="./AdGroupAdAdditionalAdvancedUrls.md">AdGroupAdAdditionalAdvancedUrls</a></td>
  <td>Landing Page URL.<br>Enter the 2nd and later of landing page URLs.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading (Advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr> 
  <tr>
  <td>advancedMobileUrl</td>
  <td>xsd:string</td>
  <td>Landing Page URL (Smartphone).</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>additionalAdvancedMobileUrls[0..9]</td>
  <td><a href="./AdGroupAdAdditionalAdvancedMobileUrls.md">AdGroupAdAdditionalAdvancedMobileUrls</a></td>
  <td>Landing page URL (Smartphone).<br>Enter the 2nd and later of landing page URLs (Smartphone).</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>Tracking URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>Custome parameters.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>*Optional if upgrading URL (advanced=TRUE).<br>*Ignore if not upgrading URL (advanced=FALSE).</td>
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
  <td>Optional<br>*Ignore if upgrading URL (advanced=TRUE).<br>*Requirement if not upgrading URL (advanced=FALSE).</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>Display URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br>*If Ad Type is Mobile App Ad or Enhanced Text Ads, it can be ignored.</td>
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
 <td>devicePreference</td>
 <td>enum <a href="./DevicePreference.md">DevicePreference</a></td>
 <td>Information of Focus Device.<br>*It enables to display your ads to smartphone devices.</td>
 <td>yes</td>
 <td>-</td>
 <td>Optional<br>*If Ad Type is Enhanced Text Ads, it can be ignored.</td>
 <td>-</td>
 <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
