# AdGroupAd
AdGroupAd objects are the data to operate Ad under Ad Group.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | Description | Restrictions | 
|---|---|---|---|
| accountId| xsd:long| Account ID| Req| Req| Req |
| campaignId| xsd:long| Campaign ID| Req| Req| Req |
| campaignName| xsd:string| Campaign name| -| -| - |
| adGroupId| xsd:long| The id of the adgroup containing this ad.| Req| Req| Req |
| adGroupName| xsd:string| Ad group name.| -| -| - |
| adId| xsd:long| Id of the Ad.| -| Req| Req |
| adTrackId| xsd:long| Ad tracking ID. <br>Production returns “0” when it is added and the value is set when ads become distribution available. <br>Sandbox always returns 0 as the adTrackID.| -| -| - |
| adName| xsd:string| Ad name.| Req| Opt| - |
| userStatus| enum<br><a href="./UserStatus.md">UserStatus</a>| User status.| Req| Opt| - |
| approvalStatus| enum<br><a href="./ApprovalStatus.md">ApprovalStatus</a>| Editoroal status.| -| -| - |
| disapprovalReasonCodes| xsd:string| Disapproval code.| -| -| - |
| ad| <a href="./Ad.md">Ad</a><br><br>			inherited <a href="./TextAd2.md">TextAd2</a><br><br>			inherited <a href="./MobileAd.md">MobileAd</a><br><br>			inherited <a href="./AppAd.md">AppAd</a>| The contents of the ad itself.<br><br>		* "Inherited TextAd" is abolished from ver.5.0.| Req| -| - |
| feedFolderId| xsd:long| Feed folder ID.| -| -| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
