# MobileAd
MobileAdオブジェクトは、スマートフォン以外の携帯電話向けの広告です。<br>
※モバイル向けサービスの提供終了により、mutate(ADD)とmutate(SET)による入稿はご利用いただけません。<br>
　なお、getによる取得やmutate(REMOVE)による削除は引き続きご利用いただけます。
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
  <td>広告の種類です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advancedUrl</td>
  <td>xsd:string</td>
  <td>リンク先URLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※URLを移行しない（advanced=FALSE）場合、Ignore。</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advancedMobileUrl</td>
  <td>xsd:string</td>
  <td>リンク先URL（スマート フォン）です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※URLを移行しない（advanced=FALSE）場合、Ignore。</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>trackingUrl</td>
  <td>xsd:string</td>
  <td>トラッキングURLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※URLを移行しない（advanced=FALSE）場合、Ignore。</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>customParameters</td>
  <td><a href="./CustomParameters.md">CustomParameters</a></td>
  <td>カスタムパラメータです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※URLを移行しない（advanced=FALSE）場合、Ignore。</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>advanced</td>
  <td>enum <a href="./Advanced.md">Advanced</a></td>
  <td>アドバンスドURL対応 のフラグです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※Default: TRUE</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>url</td>
  <td>xsd:string</td>
  <td>移行前のリンク先 URLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional<br>※URLを移行しない（advanced=FALSE）場合、Ignore。</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>displayUrl</td>
  <td>xsd:string</td>
  <td>表示URLです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement<br>※広告の種類が アプリ広告の場合、Ignore。</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>headline</td>
  <td>xsd:string</td>
  <td>タイトル文です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>description</td>
  <td>xsd:string</td>
  <td>説明文です。</td>
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
  <td>マークアップ言語です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mobileCarriers</td>
  <td>enum <a href="./CarrierName.md">CarrierName</a></td>
  <td>モバイルキャリアです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
