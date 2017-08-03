# GeoTargetType (enum)
GeoTargetTypeは、地域ターゲティングの地域判定の詳細設定を指定します。
### Service
+ [CampaignService](../services/CampaignService.md)

| Enumeration | Type | Description | 
|---|---|---|
| DONT_CARE | xsd:string | ターゲット地域設定の場合：<br>対象地域に所在する可能性があるユーザー、対象地域に関連する語句で検索したユーザー、対象地域に関心を示している可能性のあるユーザーに広告を配信します。<br>除外ターゲット地域設定の場合：<br>対象地域に所在する可能性があるユーザー、対象地域に関連する語句で検索したユーザー、対象地域に関心を示している可能性のあるユーザーには広告を配信しません。 |
| AREA_OF_INTENT | xsd:string | ターゲット地域設定の場合：<br>対象地域に関連する語句で検索したユーザーや、対象地域に関心を示している可能性のあるユーザーのみに広告を配信します。<br>※除外ターゲット地域設定の場合は選択できません。 |
| LOCATION_OF_PRESENCE | xsd:string | ターゲット地域設定の場合：<br>対象地域に所在する可能性があるユーザーにのみ、広告を配信します。<br>除外ターゲット地域設定の場合：対象地域に所在する可能性があるユーザーには、広告は配信されません。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
