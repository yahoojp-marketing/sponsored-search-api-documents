# CampaignSharedSetService
CampaignSharedSetServiceでは、対象外キーワードリストのキャンペーンへの関連付け設定などを行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
対象外キーワードリストのキャンペーンへの関連付け設定などを行います。

#### 操作
CampaignSharedSetServiceで提供される操作を説明します。
<br>

## get
キャンペーンと対象外キーワードリストの関連付け情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [CampaignSharedSetSelector](../data/CampaignSharedSetSelector.md) | getメソッドの検索条件（実行パラメータ）を保持するオブジェクトです。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignIds>100</ns1:campaignIds>
            <ns1:campaignIds>200</ns1:campaignIds>
            <ns1:campaignIds>300</ns1:campaignIds>
            <ns1:sharedListIds>1000</ns1:sharedListIds>
            <ns1:sharedListIds>1001</ns1:sharedListIds>
            <ns1:paging>
               <ns1:startIndex>4</ns1:startIndex>
               <ns1:numberResults>100</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignSharedSetPage](../data/CampaignSharedSetPage.md) | getメソッドの実行結果（全Entityのリスト）を保持するオブジェクトです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignSharedSetService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>CampaignSharedSetPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>300</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No3</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>200</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No2</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(ADD)
キャンペーンに対象外キーワードリストの関連付け設定を行います。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignSharedSetOperation](../data/CampaignSharedSetOperation.md) | mutateメソッドで操作対象となるキャンペーンと<br>対象外キーワードリストの関連付け情報を保持するオブジェクトです。| 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>200</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:campaignId>300</ns1:campaignId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignSharedSetReturnValue](../data/CampaignSharedSetReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持するオブジェクトです。 | 

#### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignSharedSetService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignSharedSetReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>200</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No2</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>300</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No3</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## mutate(REMOVE)
キャンペーンと対象外キーワードリストの関連付け設定を削除します。

### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignSharedSetOperation](../data/CampaignSharedSetOperation.md) | mutateメソッドで操作対象となるキャンペーンと<br>対象外キーワードリストの関連付け情報を保持するオブジェクトです。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>REMOVE</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>100</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1001</ns1:sharedListId>
               <ns1:campaignId>200</ns1:campaignId>
            </ns1:operand>
            <ns1:operand>
               <ns1:sharedListId>1000</ns1:sharedListId>
               <ns1:campaignId>300</ns1:campaignId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignSharedSetReturnValue](../data/CampaignSharedSetReturnValue.md) |mutateメソッドの実行結果（全Entityのリスト）を保持するオブジェクトです。 | 

#### ＜レスポンスサンプル＞
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <soapenv:Header>
      <ns1:ResponseHeader>
         <ns1:service>CampaignSharedSetService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>CampaignSharedSetReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>100</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No1</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1001</ns1:sharedListId>
                  <ns1:campaignId>200</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No2</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No2</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:campaignSharedSet>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:sharedListId>1000</ns1:sharedListId>
                  <ns1:campaignId>300</ns1:campaignId>
                  <ns1:sharedListName>Sample SharedList No1</ns1:sharedListName>
                  <ns1:campaignName>Sample Campaign No3</ns1:campaignName>
               </ns1:campaignSharedSet>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
