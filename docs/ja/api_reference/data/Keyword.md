# Keyword
Keywordオブジェクトは、キーワードに関する情報を表します。
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)
+ [CampaignCriterionService](../services/CampaignCriterionService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| Criterion(inherited)||||||
| criterionId(notupdatable)| xsd:long| クライテリアIDです。| ─| Req| Req |
| type(notupdatable)| enum<a href="./CriterionType.md">CriterionType</a>| このインスタンスのクライテリアのサブタイプを示します。| Req| Req| Req |
| Keyword||||||
| text| xsd: string| キーワードのテキストです。最大80文字、10語です。| Req| ─| ─ |
| matchType| enum <a href="./KeywordMatchType.md">KeywordMatchType</a>| キーワードのマッチタイプです。| Req| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
