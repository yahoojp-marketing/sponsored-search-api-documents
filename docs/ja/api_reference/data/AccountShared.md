# AccountShared
AccountSharedオブジェクトは、getメソッドの検索結果（全エンティティのリスト）を保持します。

### Service
+ [AccountSharedService](../services/AccountSharedService.md)

| Field | Type | Description | response | get | add | set | remove |
|---|---|---|---|---|---|---|---|
| accountId | xsd:long | アカウントIDです。 | Yes | - | - | - | - |
| sharedListId | xsd:long | 対象外キーワードリストIDです。 | Yes | - | - | Requirement<br>NotUpdatable | Requirement |
| name | xsd:string | 対象外キーワードリスト名です。 | Yes | - | Requirement | Requirement<br>Updatable | - |
| memberCount | xsd:int | 対象外キーワードリストに含まれるアイテム（検索対象外キーワード）数です。| Yes | - | - | - | - |
| referenceCount | xsd:int | 対象外キーワードリストを使用している キャンペーン数です。| Yes | - | - | - | - |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
