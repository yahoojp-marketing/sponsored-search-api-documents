# TargetingIdeaSelector
TargetingIdeaSelectorオブジェクトは、関連キーワードの提案条件を表します。
### Service
+ [TargetingIdeaService](../services/TargetingIdeaService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| searchParameters[]| <a href="../data/SearchParameter.md">SearchParameter</a><br>inherited <a href="../data/RelatedToKeywordSearchParameter.md">RelatedToKeywordSearchParameter</a><br>inherited <a href="../data/RelatedToUrlSearchParameter.md">RelatedToUrlSearchParameter</a><br>inherited <a href="../data/ExcludedKeywordSearchParameter.md">ExcludedKeywordSearchParameter</a>| 処理の対象になる提案条件が含まれます。<br><br>※ExcludedKeywordSearchParameterは、2015/11/2をもって提供を終了いたしました。|
| paging| <a href="../data/Paging.md">Paging</a>| レスポンスとして戻されるページです。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
