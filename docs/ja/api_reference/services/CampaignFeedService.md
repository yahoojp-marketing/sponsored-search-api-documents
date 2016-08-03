# CampaignFeedService
CampaignFeedServiceでは、キャンペーンのFeedItem情報の取得および更新を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/CampaignFeedService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/CampaignFeedService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### サービス概要
キャンペーンのFeedItem情報の取得およびFeedItem情報の追加・更新・削除を行います。
#### 操作
CampaignFeedServiceで提供される操作を説明します。
## get
キャンペーンのFeedItem情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [CampaignFeedSelector](../data/CampaignFeedSelector.md) | 操作の対象とするFeedItem情報です。 | 
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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:campaignIds>100000004</ns1:campaignIds>
                <ns1:feedItemIds>123</ns1:feedItemIds>
                <ns1:feedItemIds>124</ns1:feedItemIds>
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
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:campaignIds>100000004</ns1:campaignIds>
                <ns1:feedItemIds>123</ns1:feedItemIds>
                <ns1:feedItemIds>124</ns1:feedItemIds>
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
| rval | [CampaignFeedPage](../data/CampaignFeedPage.md) | 取得されるキャンペーンのFeedItem情報のエントリーです。 | 
##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignFeedService</ns1:service>
         <ns1:remainingQuota>2983</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>2.6619</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>CampaignFeedPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignFeedList>
                   <ns1:accountId>00000001</ns1:accountId>
                   <ns1:campaignId>00000003</ns1:campaignId>
                   <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   <ns1:campaignFeed>
                       <ns1:accountId>00000001</ns1:accountId>
                       <ns1:campaignId>00000003</ns1:campaignId>
                       <ns1:feedItemId>113</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:campaignFeed>
                   <ns1:campaignFeed>
                       <ns1:accountId>00000001</ns1:accountId>
                       <ns1:campaignId>00000003</ns1:campaignId>
                       <ns1:feedItemId>114</ns1:feedItemId>
                       <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   </ns1:campaignFeed>
                   <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
               </ns1:campaignFeedList>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignFeedList>
                   <ns1:accountId>00000001</ns1:accountId>
                   <ns1:campaignId>00000003</ns1:campaignId>
                   <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   <ns1:campaignFeed>
                       <ns1:accountId>00000001</ns1:accountId>
                       <ns1:campaignId>00000003</ns1:campaignId>
                       <ns1:feedItemId>115</ns1:feedItemId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                   </ns1:campaignFeed>
                </ns1:campaignFeedList>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(SET)
キャンペーンにFeedItem情報を追加・更新・解除（削除）します。 <br>
FeedItem情報を解除するときは空の情報で更新します。<br>
1つのキャンペーンに設定できるFeedItem情報は、QUICKLINKS、CALLEXTENSIONでそれぞれ20件までです。<br>
※なおCALLEXTENSIONについて1キャンペーンあたり1件の設定をお薦めします。<br>

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignFeedOperation](../data/CampaignFeedOperation.md) | 操作の対象とするキャンペーンのFeedItem情報および操作の内容を表します。<br> FeedItem情報は上書きされます。<br>FeedItem情報の設定を解除するときは空のデータで更新してください。 | 
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
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
<!-- campaignId = 100000003に対するQUICKLINKの紐付け設定 -->
                <ns1:operand>
                   <ns1:accountId>100000001</ns1:accountId>
                   <ns1:campaignId>100000003</ns1:campaignId>
                   <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   <ns1:campaignFeed>
                       <ns1:feedItemId>113</ns1:feedItemId>
                   </ns1:campaignFeed>
                   <ns1:campaignFeed>
                       <ns1:feedItemId>115</ns1:feedItemId>
                   </ns1:campaignFeed>
                 </ns1:operand>
<!-- campaignId = 100000003に対するCALLEXTENSIONの紐付け設定 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                 </ns1:operand>
<!-- campaignId = 100000007 に対するQUICKLINKの紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000007</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                </ns1:operand>
<!-- campaignId = 100000007 に対するCALLEXTENSIONの紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000007</ns1:campaignId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                </ns1:operand>
<!-- campaignId = 100000008 に対するdevicePlatformにDESKTOPを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000008</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- campaignId = 100000009 に対するdevicePlatformにSMART_PHONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000009</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- campaignId = 100000010に対するdevicePlatformにNONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000010</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
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
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
<!-- campaignId = 100000003に対するQUICKLINKの紐付け設定 -->
                <ns1:operand>
                   <ns1:accountId>100000001</ns1:accountId>
                   <ns1:campaignId>100000003</ns1:campaignId>
                   <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                   <ns1:campaignFeed>
                       <ns1:feedItemId>113</ns1:feedItemId>
                   </ns1:campaignFeed>
                   <ns1:campaignFeed>
                       <ns1:feedItemId>115</ns1:feedItemId>
                   </ns1:campaignFeed>
                   <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- campaignId = 100000003に対するCALLEXTENSIONの紐付け設定 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000003</ns1:campaignId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- campaignId = 100000007 に対するQUICKLINKの紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000007</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- campaignId = 100000007 に対するCALLEXTENSIONの紐付けの全件削除 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000007</ns1:campaignId>
                    <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
 
<!-- campaignId = 100000008 に対するdevicePlatformにDESKTOPを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000008</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                    <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                </ns1:operand>
<!-- campaignId = 100000009 に対するdevicePlatformにSMART_PHONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000009</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
                    <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                </ns1:operand>
<!-- campaignId = 100000010に対するdevicePlatformにNONEを指定した場合 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000010</ns1:campaignId>
                    <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                    <ns1:campaignFeed>
                        <ns1:feedItemId>113</ns1:feedItemId>
                    </ns1:campaignFeed>
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
| rval | [CampaignFeedReturnValue](../data/CampaignFeedReturnValue.md) | 操作結果を含むキャンペーンのFeedItem情報のコンテナです。 | 
##### ＜レスポンスサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignFeedService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignFeedReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:campaignFeed>
                            <ns1:accountId>00000001</ns1:accountId>
                            <ns1:campaignId>00000003</ns1:campaignId>
                            <ns1:feedItemId>113</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                        <ns1:campaignFeed>
                            <ns1:accountId>00000001</ns1:accountId>
                            <ns1:campaignId>00000003</ns1:campaignId>
                            <ns1:feedItemId>114</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
                        <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                    </ns1:campaignFeedList>
               </ns1:values>
               <ns1:values>
                   <ns1:operationSucceeded>true</ns1:operationSucceeded>
                   <ns1:campaignFeedList>
                       <ns1:accountId>00000001</ns1:accountId>
                       <ns1:campaignId>00000003</ns1:campaignId>
                       <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       <ns1:campaignFeed>
                           <ns1:accountId>00000001</ns1:accountId>
                           <ns1:campaignId>00000003</ns1:campaignId>
                           <ns1:feedItemId>115</ns1:feedItemId>
                           <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                       </ns1:campaignFeed>
                       <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
                   </ns1:campaignFeedList>
                </ns1:values>
<!-- setでCALLEXTENSSNIONを削除したレスポンス -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000002</ns1:campaignId>
                        <ns1:placeholderType>CALLEXTENSION</ns1:placeholderType>
                        <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                    </ns1:campaignFeedList>
                </ns1:values>
<!-- setでQUICKLINKを削除したレスポンス -->
                 <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000002</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:devicePlatform>SMART_PHONE</ns1:devicePlatform>
                    </ns1:campaignFeedList>
                </ns1:values>
 
<!-- campaignId = 00000005に対するdevicePlatformにDESKTOPを指定した場合-->
                 <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignFeedList>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000005</ns1:campaignId>
                        <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        <ns1:devicePlatform>DESKTOP</ns1:devicePlatform>
 
                        <ns1:campaignFeed>
                            <ns1:accountId>00000001</ns1:accountId>
                            <ns1:campaignId>00000005</ns1:campaignId>
                            <ns1:feedItemId>113</ns1:feedItemId>
                            <ns1:placeholderType>QUICKLINK</ns1:placeholderType>
                        </ns1:campaignFeed>
 
                    </ns1:campaignFeedList>
                </ns1:values>
 
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
