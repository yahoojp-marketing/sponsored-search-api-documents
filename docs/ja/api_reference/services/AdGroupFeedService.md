# AdGroupFeedService
AdGroupFeedServiceでは、広告グループに関するFeedItem情報の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V6.0/AdGroupFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V6.0/AdGroupFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### サービス概要
広告グループのFeedItem情報の取得およびFeedItem情報の追加・更新・削除を行います。
#### 操作
AdGroupFeedServiceで提供される操作を説明します。
## get
広告グループに設定されているFeedItem情報を取得します。
#### リクエスト

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupFeedSelector](../data/AdGroupFeedSelector.md) | 操作の対象とするFeedItem情報です。 | 
##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>xxxxxxxx</ns1:apiAccountPassword>
            <ns1:accountId>xxxxxxxx</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>xxxxxxxx</ns1:accountId>
                <ns1:campaignIds>xxxxxxxx</ns1:campaignIds>
                <ns1:campaignIds>xxxxxxxx</ns1:campaignIds>
                <ns1:campaignIds>xxxxxxxx</ns1:campaignIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:adGroupIds>xxxxxxxx</ns1:adGroupIds>
                <ns1:feedItemIds>12</ns1:feedItemIds>
                <ns1:feedItemIds>13</ns1:feedItemIds>
                <ns1:placeholderTypes>QUICKLINK</ns1:placeholderTypes>
                <ns1:placeholderTypes>CALLEXTENSION</ns1:placeholderTypes>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>00000001</ns1:accountId>
                <ns1:campaignIds>100000001</ns1:campaignIds>
                <ns1:campaignIds>100000002</ns1:campaignIds>
                <ns1:adGroupIds>100000012</ns1:adGroupIds>
                <ns1:adGroupIds>100000018</ns1:adGroupIds>
                <ns1:feedItemIds>117</ns1:feedItemIds>
                <ns1:feedItemIds>123</ns1:feedItemIds>
                <ns1:feedItemIds>125</ns1:feedItemIds>
                <ns1:placeholderTypes>QUICKLINK</ns1:placeholderTypes>
                <ns1:placeholderTypes>CALLEXTENSION</ns1:placeholderTypes>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupFeedPage](../data/AdGroupFeedPage.md) | 指定したFeedItem情報を格納するコンテナです。<br>FeedItem情報を設定していない広告グループは取得できません。 | 
##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>AdGroupFeedService</ns1:service>
         <ns1:remainingQuota>2999</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>3.5343</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>AdGroupFeedPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupFeedList>
                   <ns1:accountId>xxxxxxxx</ns1:accountId>
                   <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                   <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                   <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   <ns1:adGroupFeed>
                       <ns1:accountId>xxxxxxxx</ns1:accountId>
                       <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                       <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                       <ns1:feedItemId>123</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:adGroupFeed>
                   <ns1:adGroupFeed>
                       <ns1:accountId>xxxxxxxx</ns1:accountId>
                       <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                       <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                       <ns1:feedItemId>125</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:adGroupFeed>
                   <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
               </ns1:adGroupFeedList>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:adGroupFeedList>
                   <ns1:accountId>xxxxxxxx</ns1:accountId>
                   <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                   <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                   <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   <ns1:adGroupFeed>
                       <ns1:accountId>xxxxxxxx</ns1:accountId>
                       <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                       <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                       <ns1:feedItemId>117</ns1:feedItemId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   </ns1:adGroupFeed>
                   <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
               </ns1:adGroupFeedList>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(SET)
広告グループにFeedItem情報を追加・更新・解除（削除）します。<br> 更新は常に上書きされるため追加分を含めて更新する必要があります。<br>
FeedItem情報を解除するときは空の情報で更新します。<br>
１リクエストで異なるキャンペーン配下の広告グループに対してFeedItem情報の設定が可能です。<br>
1つの広告グループに設定できるFeedItem情報は、QUICKLINKS、CALLEXTENSIONでそれぞれ20件までです。<br>
※なおCALLEXTENSIONについて1広告グループあたり1件の設定をお薦めします。<br>

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupFeedOperation](../data/AdGroupFeedOperation.md) | 操作の対象とする広告グループのFeedItem情報および操作の内容を表します。<br> FeedItem設定は上書きされます。<br>FeedItem設定を解除するときは空のデータで更新してください。 | 
##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>00000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>00000001</ns1:accountId>
<!-- adGroupId = 100000113のQUICKLINKに対する紐付け設定 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>123</ns1:feedItemId>
                    </ns1:adGroupFeed>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>125</ns1:feedItemId>
                    </ns1:adGroupFeed>
                     </ns1:operand>
<!-- adGroupId = 100000113のCALLEXTENSIONに対する紐付け設定 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>117</ns1:feedItemId>
                    </ns1:adGroupFeed>
                </ns1:operand>
<!-- adGroupId = 100000118のQUICKLINKに対する紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
<!-- adGroupId = 100000118のCALLEXTENSIONに対する紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   </ns1:operand>
<!-- adGroupId = 100000119のdevicePlatformにDESKTOPを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000119</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- adGroupId = 100000120のdevicePlatformにSMART_PHONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000120</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- adGroupId = 100000121のdevicePlatformにNONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000121</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>NONE</ns1:devicePlatform>
                </ns1:operand> 
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>00000001</ns1:accountId>
<!-- adGroupId = 100000113のQUICKLINKに対する紐付け設定 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>123</ns1:feedItemId>
                    </ns1:adGroupFeed>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>125</ns1:feedItemId>
                    </ns1:adGroupFeed>
                     </ns1:operand>
<!-- adGroupId = 100000113のCALLEXTENSIONに対する紐付け設定 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:adGroupId>100000113</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:adGroupFeed>
                        <ns1:feedItemId>117</ns1:feedItemId>
                    </ns1:adGroupFeed>
                </ns1:operand>
<!-- adGroupId = 100000118のQUICKLINKに対する紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                             </ns1:operand>
<!-- adGroupId = 100000118のCALLEXTENSIONに対する紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000118</ns1:adGroupId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
<!-- adGroupId = 100000119のdevicePlatformにDESKTOPを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000119</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- adGroupId = 100000120のdevicePlatformにSMART_PHONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000120</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- adGroupId = 100000121のdevicePlatformにNONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>00000001</ns1:accountId>
                    <ns1:campaignId>100000004</ns1:campaignId>
                    <ns1:adGroupId>100000121</ns1:adGroupId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>NONE</ns1:devicePlatform>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupFeedReturnValue](../data/AdGroupFeedReturnValue.md) | 操作結果を含む広告グループに設定されたFeedItem情報に関するコンテナです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>xxxxxxxx</ns1:accountId>
                            <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                            <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                       </ns1:adGroupFeed>
                        <ns1:adGroupFeed>
                            <ns1:accountId>xxxxxxxx</ns1:accountId>
                            <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                            <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                            <ns1:feedItemId>125</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>xxxxxxxx</ns1:accountId>
                            <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                            <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                            <ns1:feedItemId>117</ns1:feedItemId>
                            <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        </ns1:adGroupFeed>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- setでCALLEXTENSIONを削除したレスポンス -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- setでQUICKLINKを削除したレスポンス -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- setでdevicePlatformにDESKTOPを指定したレスポンス -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>xxxxxxxx</ns1:accountId>
                            <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                            <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed> 
                        <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- setでdevicePlatformにSMART_PHONEを指定したレスポンス -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>xxxxxxxx</ns1:accountId>
                            <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                            <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed>
                        <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                    </ns1:adGroupFeedList>
                </ns1:values>
<!-- setでdevicePlatformにNONEを指定したレスポンス -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupFeedList>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:adGroupFeed>
                            <ns1:accountId>xxxxxxxx</ns1:accountId>
                            <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                            <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                            <ns1:feedItemId>123</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:adGroupFeed>
                        <ns1:devicePlatform>NONE</ns1:devicePlatform>
                    </ns1:adGroupFeedList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
