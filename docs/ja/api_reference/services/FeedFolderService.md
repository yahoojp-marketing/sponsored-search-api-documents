# FeedFolderService
FeedFolderServiceでは、自動データ挿入のリスト情報の取得および追加・更新・削除を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/FeedFolderService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/FeedFolderService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### サービス概要
自動データ挿入のリスト情報の取得および追加・更新・削除を行います。
#### 操作
FeedFoldersServiceで提供される操作を説明します。
## get
自動データ挿入のリスト情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [FeedFolderSelector](../data/FeedFolderSelector.md) | 操作の対象とする自動データ挿入のリスト情報です。 | 
＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:feedFolderIds>12</ns1:feedFolderIds>
                <ns1:feedFolderIds>13</ns1:feedFolderIds>
                <ns1:feedFolderIds>14</ns1:feedFolderIds>
                <ns1:feedFolderName>FeedFolderName</ns1:feedFolderName>
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
正常時のレスポンスフィールド

| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [FeedFolderPage](../data/FeedFolderPage.md) | 取得される自動データ挿入のリスト情報に関するエントリーです。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
               <ns1:totalNumEntries>3</ns1:totalNumEntries>
                <ns1:Page.Type>FeedFolderPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
FeedItem情報を追加します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [FeedFolderOperation](../data/FeedFolderOperation.md) | 操作の対象とする自動データ挿入のリスト情報と処理の内容です。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                    <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname1</ns1:feed AttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                    </ns1:feedAttribute>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname2</ns1:feed AttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                    </ns1:feedAttribute>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolderReturnValue.md) | 操作結果を含むFeedItem情報のコンテナです。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedFolderReturnValue</ns1:ListReturn Value.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(SET)
FeedItem情報を更新します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [FeedFolderOperation](../data/FeedFolderOperation.md) | 操作の対象とする自動データ挿入のリスト情報と処理の内容です。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderId>100000001</ns1:feedFolderId>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname1</ns1:feed AttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                    </ns1:feedAttribute>
                    <ns1:feedAttribute>
                        <ns1:feedAttributeName>myfeedattname2</ns1:feed AttributeName>
                        <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                    </ns1:feedAttribute>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolderReturnValue.md) | 操作結果を含む自動データ挿入のリスト情報のコンテナです。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedFolderReturnValue</ns1:ListReturn Value.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(REMOVE)
FeedItem情報を削除します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [FeedFolderOperation](../data/FeedFolderOperation.md) | 操作の対象とするFeedItem情報です。 | 
＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:feedFolderId>100000001</ns1:feedFolderId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [FeedFolderReturnValue](../data/FeedFolderReturnValue.md) | 操作結果を含む自動データ挿入のリスト情報のコンテナです。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>FeedFolderService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>FeedFolderReturnValue</ns1:ListReturn Value.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:feedFolder>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:feedFolderId>113</ns1:feedFolderId>
                        <ns1:feedFolderName>myfeedname</ns1:feedFolderName>
                        <ns1:placeholderType>AD_CUSTOMIZER</ns1:placeholder Type>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000001</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname1</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_INTEGER </ns1:placeholderField>
                        </ns1:feedAttribute>
                        <ns1:feedAttribute>
                            <ns1:feedAttributeId>2000000002</ns1:feedAttributeId>
                            <ns1:feedAttributeName>myfeedattname2</ns1:feed AttributeName>
                            <ns1:placeholderField>AD_CUSTOMIZER_PRICE </ns1:placeholderField>
                        </ns1:feedAttribute>
                    </ns1:feedFolder>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
