# CampaignRetargetingListService
CampaignRetargetingListServiceでは、キャンペーン階層におけるターゲットリストの設定（設定情報の取得、追加、更新、削除）を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/CampaignRetargetingListService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/CampaignRetargetingListService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
キャンペーン階層におけるターゲットリストの設定（設定情報の取得、追加、更新、削除）を行います。

#### 操作
CampaignRetargetingListServiceで提供される操作を説明します。

## get
キャンペーン階層におけるターゲットリストの設定情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [CampaignRetargetingListSelector](../data/CampaignRetargetingListSelector.md) | getメソッドの検索条件（実行パラメータ）を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:campaignIds>100000002</ns1:campaignIds>
        <ns1:campaignIds>100000003</ns1:campaignIds>
        <ns1:campaignIds>100000004</ns1:campaignIds>
        <ns1:targetListIds>100000005</ns1:targetListIds>
        <ns1:targetListIds>100000006</ns1:targetListIds>
        <ns1:targetListIds>100000007</ns1:targetListIds>
        <ns1:excludedType>INCLUDED</ns1:excludedType>
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
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignRetargetingListPage](../data/CampaignRetargetingListPage.md) | getメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignRetargetingListService</ns1:service>
            <ns1:remainingQuota>-1</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>CampaignRetargetingListPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignRetargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:criterionTargetList>
                            <ns1:targetListId>1000000003</ns1:targetListId>
                            <ns1:targetListName>targetList name</ns1:targetListName>
                        </ns1:criterionTargetList>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:bidMultiplier>0.2</ns1:bidMultiplier>
                    </ns1:campaignRetargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
キャンペーン階層におけるターゲットリストの設定情報を追加します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignRetargetingListOperation](../data/CampaignRetargetingListOperation.md) | mutateメソッドで操作対象となるターゲットリストと処理内容を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:criterionTargetList>
                        <ns1:targetListId>100000003</ns1:targetListId>
                    </ns1:criterionTargetList>
                    <ns1:excludedType>INCLUDED</ns1:excludedType>
                    <ns1:bidMultiplier>0.3</ns1:bidMultiplier>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:criterionTargetList>
                        <ns1:targetListId>100000004</ns1:targetListId>
                    </ns1:criterionTargetList>
                    <ns1:excludedType>EXCLUDED</ns1:excludedType>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignRetargetingListReturnValue](../data/CampaignRetargetingListReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignRetargetingListService</ns1:service>
            <ns1:remainingQuota>-1</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.9414</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignRetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignRetargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:criterionTargetList>
                            <ns1:targetListId>1000000003</ns1:targetListId>
                            <ns1:targetListName>targetList 1000000003</ns1:targetListName>
                        </ns1:criterionTargetList>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:bidMultiplier>0.3</ns1:bidMultiplier>
                    </ns1:campaignRetargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignRetargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:criterionTargetList>
                            <ns1:targetListId>1000000004</ns1:targetListId>
                            <ns1:targetListName>targetList 1000000004</ns1:targetListName>
                        </ns1:criterionTargetList>
                        <ns1:excludedType>EXCLUDED</ns1:excludedType>
                   </ns1:campaignRetargetingList>
                </ns1:values>             
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
キャンペーン階層におけるターゲットリストの設定情報を更新します。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignRetargetingListOperation](../data/CampaignRetargetingListOperation.md) | mutateメソッドで操作対象となるターゲットリストと処理内容を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:criterionTargetList>
                        <ns1:targetListId>100000003</ns1:targetListId>
                    </ns1:criterionTargetList>
                    <ns1:bidMultiplier>1.3</ns1:bidMultiplier>
                </ns1:operand>
                <!-- 除外 から 配信に変更 -->
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:criterionTargetList>
                        <ns1:targetListId>100000003</ns1:targetListId>
                    </ns1:criterionTargetList>
                    <ns1:excludedType>INCLUDED</ns1:excludedType>
                    <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
                </ns1:operand>               
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignRetargetingListReturnValue](../data/CampaignRetargetingListReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignRetargetingListService</ns1:service>
            <ns1:remainingQuota>-1</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.9414</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignRetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignRetargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:criterionTargetList>
                            <ns1:targetListId>1000000003</ns1:targetListId>
                            <ns1:targetListName>targetList 1000000003</ns1:targetListName>
                        </ns1:criterionTargetList>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:bidMultiplier>1.3</ns1:bidMultiplier>
                    </ns1:campaignRetargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignRetargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:criterionTargetList>
                            <ns1:targetListId>1000000004</ns1:targetListId>
                            <ns1:targetListName>targetList 1000000004</ns1:targetListName>
                        </ns1:criterionTargetList>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
                   </ns1:campaignRetargetingList>
                </ns1:values>             
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
キャンペーン階層におけるターゲットリストの設定情報を削除します。

#### リクエスト

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [CampaignRetargetingListOperation](../data/CampaignRetargetingListOperation.md) | mutateメソッドで操作対象となるターゲットリストと処理内容を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>100000001</ns1:accountId>
                    <ns1:campaignId>100000002</ns1:campaignId>
                    <ns1:excludedType>INCLUDED</ns1:excludedType>
                    <ns1:criterionTargetList>
                        <ns1:targetListId>100000003</ns1:targetListId>
                    </ns1:criterionTargetList>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [CampaignRetargetingListReturnValue](../data/CampaignRetargetingListReturnValue.md) | mutateメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignRetargetingListService</ns1:service>
            <ns1:remainingQuota>-1</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.9414</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignRetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignRetargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000002</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:criterionTargetList>
                            <ns1:targetListId>1000000003</ns1:targetListId>
                            <ns1:targetListName>targetList 1000000003</ns1:targetListName>
                        </ns1:criterionTargetList>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:bidMultiplier>0.3</ns1:bidMultiplier>
                    </ns1:campaignRetargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
