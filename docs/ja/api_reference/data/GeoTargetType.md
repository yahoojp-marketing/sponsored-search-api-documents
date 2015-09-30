# GeoTargetType (enum)
GeoTargetTypeは、地域ターゲティングの地域判定の詳細設定を指定します。
### Service
+ [CampaignService](../services/CampaignService.md)

| 値 | データ型 | 説明 | 
|---|---|---|
| DONT_CARE| string| ターゲット地域設定の場合：検索クエリーとユーザの現在地のどちらかに一致した場合でも広告は配信されます。<br>除外ターゲット地域設定の場合：検索クエリーと現在地のいずれかに一致した場合、広告は配信されません。 |
| AREA_OF_INTENT| string| ターゲット地域設定の場合：検索クエリーが一致した場合のみ、広告が配信されます。<br>※除外ターゲット地域設定の場合は選択できません。 |
| LOCATION_OF_PRESENCE| string| ターゲット地域設定の場合：ユーザの現在地が一致した場合のみ、広告が配信されます。<br>除外ターゲット地域設定の場合：ユーザーの現在地が一致した場合、広告が配信されません。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
