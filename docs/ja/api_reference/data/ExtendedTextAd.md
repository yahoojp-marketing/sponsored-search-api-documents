# ExtendedTextAd
 ExtendedTextAdオブジェクトは、拡大テキスト広告に関する情報を表します。

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

### Inheritance
+ [Ad](./Ad.md)

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
  <td>headline2</td>
  <td>xsd:string</td>
  <td>2行目のタイトルです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>path1</td>
  <td>xsd:string</td>
  <td>自動作成される表示URLを補足するパスです。<br>※path2を指定する場合は、path1は必須。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※default:null</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>path2</td>
  <td>xsd:string</td>
  <td>自動作成される表示URLを補足するパスです。<br>※path1を指定していない場合、path2はIgnore。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※default:null</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
