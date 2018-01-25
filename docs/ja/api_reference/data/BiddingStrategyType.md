# BiddingStrategyType (enum)
BiddingStrategyTypeは、自動入札タイプを表します。

### Service
+ [AdGroupService](../services/AdGroupService.md)
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignService](../services/CampaignService.md)

<table>
 <tr>
  <th>Enumeration </th>
  <th>Type</th>
  <th>Description</th>
 <tr>
  <td>BUDGET_OPTIMIZER</td>
  <td>xsd:string</td>
  <td>入札価格の上限金額を設定しない自動入札です。<br>※現在は設定できません。<br>※この項目を設定していたキャンペーンには、2017年4月12日にTARGET_SPENDが設定されました。</td>
 </tr>
 <tr>
  <td>MANUAL_CPC</td>
  <td>xsd:string</td>
  <td>手動で入札を行います。<br>※キャンペーンに適用可能です。広告グループには現在設定できません。</td>
 </tr>
 <tr>
  <td>PAGE_ONE_PROMOTED</td>
  <td>xsd:string</td>
  <td>検索結果ページの目標掲載位置です。<br>※キャンペーンに適用可能です。広告グループには現在設定できません。</td>
 </tr>
 <tr>
  <td>TARGET_ROAS</td>
  <td>xsd:string</td>
  <td>広告費用対効果の目標値です。<br>※キャンペーンの更新時のみ適用可能です。広告グループには現在設定できません。</td>
 </tr>
 <tr>
  <td>TARGET_SPEND</td>
  <td>xsd:string</td>
  <td>クリック数を最大化します。<br>※キャンペーンに適用可能です。広告グループには現在設定できません。</td>
 </tr>
 <tr>
  <td>ENHANCED_CPC</td>
  <td>xsd:string</td>
  <td>コンバージョン数を最大化します。<br>※キャンペーンに適用可能です。広告グループには現在設定できません。</td>
 </tr>
 <tr>
  <td>TARGET_CPA</td>
  <td>xsd:string</td>
  <td>コンバージョン単価の目標値です。<br>※キャンペーンの更新時のみ適用可能です。広告グループには現在設定できません。</td>
 </tr>
 <tr>
  <td>NONE</td>
  <td>xsd:string</td>
  <td>設定した入札設定を取り消して、上位エンティティの入札設定に従う場合に指定します。<br>広告グループ、キーワードの入札設定を削除する場合に使用します。</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
