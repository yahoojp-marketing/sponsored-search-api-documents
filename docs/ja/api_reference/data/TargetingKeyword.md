# TargetingKeyword
TargetingKeywordオブジェクトは、データ自動挿入のターゲットキーワードを表します。
### Service
+ [FeedItemService](../services/FeedItemService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| targetingKeywordId| long| 1| 0| ○| Ignore| Optional| Ignore| 指定したキーワード(text)を識別するIDになります。<br>※設定を解除する場合は「0」 を指定してください。 |
| text| string| 1| 0| ○| Requirement| Requirement| Ignore| 指定するキーワードです。<br>入力制限は80文字以内10ワードまでになります。 |
| matchType| enum <a href="./KeywordMatchType.md">KeywordMatchType</a>| 1| 0| ○| Requirement| Requirement| Ignore| マッチタイプです。<br>入力されたキーワードが検索クエリにどのように一致するかを示します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
