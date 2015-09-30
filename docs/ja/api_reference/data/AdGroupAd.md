# AdGroupAd
AdGroupAdオブジェクトは、広告に関する操作を行うための情報を表します。
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId(notupdatable)| xsd:long| アカウントIDです。| Req| Req| Req |
| campaignid(notupdatable)| xsd:long| キャンペーンIDです。| Req| Req| Req |
| campaignName(notupdatable)| xsd:string| キャンペーン名です。| ─| ─| ─ |
| adGroupId(notupdatable)| xsd:long| 広告グループIDです。| Req| Req| Req |
| adGroupName| xsd:string| 広告グループ名です。| ─| ─| ─ |
| adId| xsd:long| 広告IDです。| ─| Req| Req |
| adTrackId| xsd:long| 広告IDを示すトラッキング用のIDです。この値は追加時は常に0が返り、広告が配信可能になった段階で値が設定されます。※Sandbox環境では常に0が返ります| ─| ─| ─ |
| adName(updatable)| xsd:string| 広告名です。| Req| Opt| ─ |
| userStatus(updatable)| enum <a href="../data/UserStatus.md">UserStatus</a>| ユーザーにより設定される掲載状況です。| Req| Opt| ─ |
| approvalStatus| enum <a href="../data/ApprovalStatus.md">ApprovalStatus</a>| 審査の状況です。| ─| ─| ─ |
| disapprovalReasonCodes| xsd:string| 審査否認理由のコードです。<br>各コードのその内容は、<a href="../appendix/ed_reasons.md"><span>Editorial Reason Text</span></a>を参照してください。| ─| ─| ─ |
| ad(notupdatable)| <a href="../data/Ad.md">Ad</a><br><br> inherited <a href="../data/TextAd2.md">TextAd2</a><br> inherited <a href="../data/MobileAd.md">MobileAd</a><br> inherited <a href="../data/AppAd.md">AppAd</a>| 広告です。| Req| ─| ─ |
| feedFolderId| xsd:long| フィードフォルダIDです。| ─| ─| ─ |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
