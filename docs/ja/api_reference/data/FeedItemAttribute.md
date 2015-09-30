# FeedItemAttribute
FeedItemAttributeオブジェクトは、FeedItem情報の値を格納します。
### Service
+ [FeedItemService](../services/FeedItemService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| placeholderField| enum <a href="./PlaceholderField_FeedItem.md">PlaceholderField</a>| 1| 0| ○| Requirement（データ自動挿入のみ：Ignore）| Requirement（データ自動挿入のみ：Ignore）| Ignore| FeedItem情報の種類です。 |
| feedAttributeId| long| 1| 0| ○| Ignore（データ自動挿入のみ：Requirement）| Ignore（データ自動挿入のみ：Requirement）| Ignore| Feed属性IDです。 |
| feedAttributeValue| string| 1| 0| ○| Requirement| Requirement| Ignore| FeedItem情報の値です。 更新するときは、このフィールドに値を入力してmutate(SET)リクエストします。<br>※リクエストでは、mutate(ADD)およびmutate(SET)で指定したFeedItem情報の値が入力されます。<br>※レスポンスでは、審査状況が審査中、または配信中の情報が入力されます。<br>※データ自動挿入をご利用の場合は、各属性については以下のように入力してください：<br>・AD_CUSTOMIZER_INTEGER<br>ex) 99999999<br>・AD_CUSTOMIZER_PRICE<br>ex) 19800 or 19,800<br>・AD_CUSTOMIZER_DATE<br>ex) 20151231 235959<br>・AD_CUSTOMIZER_STRING<br>ex) home |
| reviewFeedAttributeValue| enum <a href="./ApprovalStatus.md">ApprovalStatus</a>| 1| 0| ○※| Ignore| Ignore| Ignore| FeedItem情報が審査中のときのみレスポンスされます。審査が完了するとフィールドが含まれなくなります。<br>※リクエストではこのフィールドは使用しません。<br>※レスポンスでは、審査状況が再審査中か、配信審査中の場合のみ、審査中の情報が設定されます。<br>※データ自動挿入のみ、reviewFeedAttributeValueを利用されず、feed AttributeValueで表示がそのまま置き換わります。<br>（審査中及び掲載不可の場合は配信が自動的に停止されます。） |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
