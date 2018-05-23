# RetargetingListSelector
RetargetingListSelectorは、ターゲットリストのgetメソッド検索条件（実行パラメータ）を保持するオブジェクトです。

### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>get</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>検索条件：アカウントIDです。</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>targetListIds[0...1000]</td>
  <td>xsd:long</td>
  <td>検索条件：ターゲットリストIDです。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>targetListTypes[0...3]</td>
  <td>enum <a href="TargetListType.md">TargetListType</a></td>
  <td>検索条件：ターゲットリストの種類です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>owner</td>
  <td>enum <a href="TargetListOwner.md">TargetListOwner</a></td>
  <td>検索条件：ターゲットリストの所有状態です。</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>検索条件：取得範囲です。</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
