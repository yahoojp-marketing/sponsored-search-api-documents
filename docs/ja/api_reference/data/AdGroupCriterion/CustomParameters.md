# CustomParameters
CustomParametersオブジェクトは、カスタムパラメータの設定を表します。

### Service
+ [AdGroupCriterionService](../../services/AdGroupCriterionService.md)

### Namespace
[AdGroupCriterionService#Namespace](../../services/AdGroupCriterionService.md#namespace)

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
  <td>isRemove</td>
  <td>enum <a href="IsRemove.md">IsRemove</a></td>
  <td>削除フラグです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Optional</td>
  <td>-</td>
 </tr>
 <tr>
  <td>parameters[0...3]</td>
  <td><a href="CustomParameter.md">CustomParameter</a></td>
  <td>パラメータです。<br>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>※既存の項目を置き換え ます。<br>※削除フラグを立てた（isRemove=TRUE）場合、Ignore。こちらの項目関係なく 全項目が削除されます。</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
