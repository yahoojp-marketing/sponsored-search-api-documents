# FeedItemAttribute
FeedItemAttribute contains the value of FeedItem information.
### Service
+ [FeedItemService](../services/FeedItemService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| placeholderField| enum <a href="./PlaceholderField_FeedItem.md">PlaceholderField</a>| 1| 0| yes| Requirement| Requirement| Ignore| FeedItem information type |
| feedAttributeId| long| 1| 0| yes| Ignore (AD_CUSTOMIZER: Requirement)| Ignore (AD_CUSTOMIZER: Requirement)| Ignore| Feed attribute ID. |
| feedAttributeValue| long| 1| 0| yes| Requirement| Requirement| Ignore| FeedItem information value<br>For update, insert value in this field and request set<br>* In request, value of FeedItem information can be inserted from add and set<br>* In response, information will appear when it is in review or in approved status<br>* For data auto insertion insert the value as follows:<br>・AD_CUSTOMIZER_INTEGER<br>ex) 99999999<br>・AD_CUSTOMIZER_PRICE<br>ex) 19800 or 19,800<br>・AD_CUSTOMIZER_DATE<br>ex) 20151231 235959<br>・AD_CUSTOMIZER_STRING<br>ex) home |
| reviewFeedAttributeValue| string| 1| 0| yes※| Ignore| Ignore| Ignore| Responded only when FeedItem information is in review<br>Field will not appear after the review is done<br>* In request, this field will not be used<br>* In response, information will appear when it is in disapproved with review or in delivery review. <br>*This will not be used for data auto insertion. (If the review is disapproved, the ad will stop the display) |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
