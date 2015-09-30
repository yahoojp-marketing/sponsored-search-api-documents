# Bid [AdGroupCriterionService]
Bidオブジェクトは、入札価格を表示します。（AdGroupCriterionService用のオブジェクトです。）
### Service
+ [AdGroupCriterionService](../services/AdGroupCriterionService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| maxCpc| xsd:long| キーワード入札価格です。（1-50000）<br>※maxCpcが「0」の場合は、設定なしと同様です。| Opt| Opt<br>                    (updatable)| - |
| bidSource| enum <a href="../data/BidSource.md">BidSource</a>| 入札価格ソースです。| -| -| - |
| adGroupMaxCpc| xsd:long| 広告グループ入札価格です。| -| -| - |
| keywordMaxCpc| xsd:long| キーワード入札価格です。| -| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
