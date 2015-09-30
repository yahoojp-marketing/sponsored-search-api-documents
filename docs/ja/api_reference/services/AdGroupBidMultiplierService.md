# AdGroupBidMultiplierService
AdGroupBidMultiplierServiceでは、広告グループに関する入札価格調整率の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.2/AdGroupBidMultiplierService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.2/AdGroupBidMultiplierService?wsdl |
#### Namespace
http://ss.yahooapis.jp/V5
#### サービス概要
広告グループに関する入札価格調整率の取得および追加・更新・削除を行います。
#### 操作
AdGroupBidMultiplierServiceで提供される操作を説明します。
## get
広告グループに関する入札価格調整率を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupBidMultiplierSelector](../data/AdGroupBidMultiplierSelector.md) | 操作の対象とする広告グループの入札価格調整率です。 | 
##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:accountId>00000001</ns1:accountId>
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:campaignIds>100000004</ns1:campaignIds>
                <ns1:adGroupIds>100000005</ns1:adGroupIds>
                <ns1:adGroupIds>100000006</ns1:adGroupIds>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:campaignIds>100000004</ns1:campaignIds>
                <ns1:adGroupIds>100000005</ns1:adGroupIds>
                <ns1:adGroupIds>100000006</ns1:adGroupIds>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupBidMultiplierPage](../data/AdGroupBidMultiplierPage.md) | 取得される広告グループの入札価格調整率のエントリーです。 | 
##### ＜レスポンスサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupBidMultiplierService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:Page.Type>AdGroupBidMultiplierPage</ns1:Page.Type>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:bidMultipliers xsi:type="ns1:PlatformBidMultiplierList">
                            <ns1:type>PLATFORM</ns1:type>
                            <ns1:bidMultipliers>
                                <ns1:type>PLATFORM</ns1:type>
                                <ns1:platformName>SMART_PHONE</ns1:platformName>
                                <ns1:bidMultiplier>0.10</ns1:bidMultiplier>
                            </ns1:bidMultipliers>
                        </ns1:bidMultipliers>
                    </ns1:adGroupBidMultiplier>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:bidMultipliers xsi:type="ns1:PlatformBidMultiplierList">
                            <ns1:type>PLATFORM</ns1:type>
                            <ns1:bidMultipliers>
                                <ns1:type>PLATFORM</ns1:type>
                                <ns1:platformName>SMART_PHONE</ns1:platformName>
                                <ns1:bidMultiplier>2</ns1:bidMultiplier>
                            </ns1:bidMultipliers>
                        </ns1:bidMultipliers>
                    </ns1:adGroupBidMultiplier>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループに関する入札価格調整率を更新します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupBidMultiplierOperation](../data/AdGroupBidMultiplierOperation.md) | 操作の対象となる広告グループの入札価格調整率と処理の内容です。 | 
##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                <ns1:campaignId>1000000003</ns1:campaignId>
                <ns1:operand>                    
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                    
                    <ns1:bidMultipliers xsi:type="ns1:PlatformBidMultiplierList">
                        <ns1:type>PLATFORM</ns1:type>
                        <ns1:bidMultipliers>
                            <ns1:type>PLATFORM</ns1:type>
                            <ns1:platformName>SMART_PHONE</ns1:platformName>
                            <ns1:bidMultiplier>0.10</ns1:bidMultiplier>
                        </ns1:bidMultipliers>                        
                    </ns1:bidMultipliers>                   
                </ns1:operand>
<!-- Bid調整率の設定をクリアする場合 -->
                <ns1:operand>                    
                    <ns1:adGroupId>1000000006</ns1:adGroupId>
                    <ns1:bidMultipliers xsi:type="ns1:PlatformBidMultiplierList">
                        <ns1:type>PLATFORM</ns1:type>
                        <ns1:bidMultipliers>
                            <ns1:type>PLATFORM</ns1:type>
                            <ns1:platformName>SMART_PHONE</ns1:platformName>
                        </ns1:bidMultipliers>                        
                    </ns1:bidMultipliers>                   
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                <ns1:campaignId>1000000003</ns1:campaignId>
                <ns1:operand>                    
                    <ns1:adGroupId>1000000005</ns1:adGroupId>                    
                    <ns1:bidMultipliers xsi:type="ns1:PlatformBidMultiplierList">
                        <ns1:type>PLATFORM</ns1:type>
                        <ns1:bidMultipliers>
                            <ns1:type>PLATFORM</ns1:type>
                            <ns1:platformName>SMART_PHONE</ns1:platformName>
                            <ns1:bidMultiplier>0.10</ns1:bidMultiplier>
                        </ns1:bidMultipliers>                        
                    </ns1:bidMultipliers>                   
                </ns1:operand>
<!-- Bid調整率の設定をクリアする場合 -->
                <ns1:operand>                    
                    <ns1:adGroupId>1000000006</ns1:adGroupId>                    
                    <ns1:bidMultipliers xsi:type="ns1:PlatformBidMultiplierList">
                        <ns1:type>PLATFORM</ns1:type>
                        <ns1:bidMultipliers>
                            <ns1:type>PLATFORM</ns1:type>
                            <ns1:platformName>SMART_PHONE</ns1:platformName>
                        </ns1:bidMultipliers>                        
                    </ns1:bidMultipliers>                   
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupBidMultiplierReturnValue](../data/AdGroupBidMultiplierReturnValue.md) | 操作結果を含む広告グループの入札価格調整率に関する情報のコンテナです。 | 
##### ＜レスポンスサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupBidMultiplierService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupBidMultiplierReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                        <ns1:bidMultipliers xsi:type="ns1:PlatformBidMultiplierList">
                            <ns1:type>PLATFORM</ns1:type>
                            <ns1:bidMultipliers>
                                <ns1:type>PLATFORM</ns1:type>
                                <ns1:platformName>SMART_PHONE</ns1:platformName>
                                <ns1:bidMultiplier>0.10</ns1:bidMultiplier>
                            </ns1:bidMultipliers>
                        </ns1:bidMultipliers>
                    </ns1:adGroupBidMultiplier>
                </ns1:values>
<!-- Bid調整率の設定がない場合のレスポンス -->
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupBidMultiplier>
                        <ns1:accountId>xxxxxxxx</ns1:accountId>
                        <ns1:campaignId>xxxxxxxx</ns1:campaignId>
                        <ns1:adGroupId>xxxxxxxx</ns1:adGroupId>
                    </ns1:adGroupBidMultiplier>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
