# GeoTargetType (enum)
GeoTargetType specifies Advanced Location options of Geo Targeting.

### Service
+ [CampaignService](../services/CampaignService.md)

| Value | Description | 
|---|---|
| DON'T_CARE| Positive Geo Target:<br>Ads are displayed if either search query or physical geo location are matched.<br>Negative Geo Target:<br>Ads are NOT displayed even if either search query or physical geo location are matched |
| AREA_OF_INTENT| Positive Geo Target:<br>Ads are displayed if search query is matched.<br>*This is not selectable in the Campaign with Negative Geo Target. |
| LOCATION_OF_PRESENCE| Positive Geo Target:<br>Ads are displayed if physiclal geo location of the user is matched. <br>Negative Geo Target:<br>Ads are NOT displayed if physiclal geo location of the user is matched. |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
