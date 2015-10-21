# BulkService
BulkServiceは、バルクシートを使用した一括ダウンロード・一括アップロードの機能を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.3/BulkService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.3/BulkService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V5
#### サービス概要
バルクシートを使用した一括ダウンロード・一括アップロードの機能を提供します。
##### ダウンロード処理の流れ
1. getBulkDownloadで、一括ダウンロードをするデータをリクエストします。
2. レスポンス内に含まれるdownloadBulkJobId（以下バルクID）を取得します。
3. 取得したバルクIDを利用し、getBulkDownloadStatusでステータスを確認します。
4. ステータスが"COMPLETED"ならば、レスポンスにダウンロードURLが戻ります。
5. ステータスが"IN_PROGRESS"ならば、一定時間をおき再度ステータスの確認を実施します。
6. ステータスが"SYSTEM_ERROR"であれば、ダウンロードURLは戻りません。再度一括ダウンロードのリクエストを実施します。
7. ステータスが"TIMEOUT"（タイムアウト）ならば、再度一括ダウンロードのリクエストを実施します。問題が解決しない場合は、弊社API担当者まで連絡をして下さい。
<br><br>
【注意事項】<br>
・セキュリティ上、ダウンロードURLは15分間のみ有効です。<br>　URL取得後、15分経過した場合は、再度getBulkDownloadにて新規のダウンロードURLを取得して下さい。<br>
・ダウンロードファイルには、削除されたアカウントおよびキャンペーン情報は含まれません。<br>
・getBulkDownloadでURLを作成した、IPアドレスでのみダウンロードが処理が可能です。

##### アップロード処理の流れ
1. getUploadUrlで一括アップロード用のURLをリクエストします。
2. アップロード用のURLがレスポンスとして戻されます。
3. アップロードURLにバルクシートのアップロード処理を実施します。
4.アップロード処理が完了すると、HTTPのレスポンス内に含まれる、uploadBulkJobId（以下バルクID）を取得します。
5. uploadBulkJobIdをもとに、getBulkUploadStatusでアップロードのステータスを取得します。
6. ステータスが"COMPLETED"ならば、アップロード処理が正常に終了しました。
7. ステータスが"IN_PROGRESS"ならば、アップロード処理の実行中です。ステータスの確認を完了になるまで実施してください。
<br><br>
【注意事項】<br>
・セキュリティ上、アップロードURLは15分間のみ有効です。<br>　URL取得後、15分経過した場合は、再度getUploadUrlにて新規のアップロードURLを取得して下さい。<br>
・getUploadUrlでURLを作成した、IPアドレスでのみアップロード処理が可能です。<br>
・アップロード後、入稿処理が完了するまで次のファイルをアップロードできません。<br>
・同時に複数のバルクシートをアップロードはできません。これは管理画面も含みます。<br>
・アップロード可能ファイルサイズは1回あたり20MB（非圧縮）までです。<br>
・アップロード可能な行数は、1日に原則15万行までです。

#### 操作
BulkServiceで提供される操作を説明します。 

## getBulkDownload
#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [BulkDownloadSelector](../data/BulkDownloadSelector.md) | 一括取得する対象を定義します。 | 


##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
      <ns1:getBulkDownload>
      <ns1:selector>
        <ns1:accountId>00000001</ns1:accountId>
        <ns1:campaignUserStatuses>ACTIVE</ns1:campaignUserStatuses>
        <ns1:adGroupUserStatuses>ACTIVE</ns1:adGroupUserStatuses>
        <ns1:adGroupAdUserStatuses>ACTIVE</ns1:adGroupAdUserStatuses>
        <ns1:adGroupCriterionUserStatuses>ACTIVE</ns1:adGroupCriterionUserStatuses>
        <ns1:adGroupAdApprovalStatuses>APPROVED</ns1:adGroupAdApprovalStatuses>
        <ns1:adGroupAdApprovalStatuses>APPROVED_WITH_REVIEW</ns1:adGroupAdApprovalStatuses>
        <ns1:adGroupAdApprovalStatuses>REVIEW</ns1:adGroupAdApprovalStatuses>
        <ns1:adGroupAdApprovalStatuses>PRE_DISAPPROVED</ns1:adGroupAdApprovalStatuses>
        <ns1:adGroupAdApprovalStatuses>POST_DISAPPROVED</ns1:adGroupAdApprovalStatuses>
        <ns1:adGroupCriterionApprovalStatuses>APPROVED</ns1:adGroupCriterionApprovalStatuses>
        <ns1:adGroupCriterionApprovalStatuses>APPROVED_WITH_REVIEW</ns1:adGroupCriterionApprovalStatuses>
        <ns1:adGroupCriterionApprovalStatuses>REVIEW</ns1:adGroupCriterionApprovalStatuses>
        <ns1:adGroupCriterionApprovalStatuses>PRE_DISAPPROVED</ns1:adGroupCriterionApprovalStatuses>
        <ns1:adGroupCriterionApprovalStatuses>POST_DISAPPROVED</ns1:adGroupCriterionApprovalStatuses>
        <ns1:entityTypes>ALL</ns1:entityTypes>
        <ns1:downloadBulkJob>
          <ns1:downloadBulkJobName>ダウンロードジョブ</ns1:downloadBulkJobName>
        </ns1:downloadBulkJob>
        <ns1:lang>JA</ns1:lang>
        <ns1:output>CSV</ns1:output>
        <ns1:encoding>SJIS</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/BulkDownloadReturnValue.md) | ダウンロードの処理結果を格納するコンテナです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>BulkService</ns1:service>
      <ns1:remainingQuota>129984</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>1.1229</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownloadResponse>
      <ns1:rval>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:downloadBulkJob>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:downloadBulkJobId>42</ns1:downloadBulkJobId>
            <ns1:downloadBulkUserName>8983-5689-9971-5970</ns1:downloadBulkUserName>
            <ns1:downloadBulkStartDate>2011-09-07T22:55:37+09:00</ns1:downloadBulkStartDate>
            <ns1:downloadJobStatus>IN_PROGRESS</ns1:downloadJobStatus>
            <ns1:progress>0</ns1:progress>
          </ns1:downloadBulkJob>
        </ns1:values>
      </ns1:rval>
    </ns1:getBulkDownloadResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## getBulkDownloadStatus
#### リクエスト
一括ダウンロードの処理状況を確認し、ダウンロード元のURLを取得します。

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| selector | ○ | [BulkDownloadStatusSelector](../data/BulkDownloadStatusSelector.md) | 取得する対象を定義します。 | 
##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
        <ns1:getBulkDownloadStatus>
            <ns1:selector>
                <ns1:accountId>00000001</ns1:accountId>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobIds>xxxxxxxxxxxxxx</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobStatuses>COMPLETED</ns1:downloadBulkJobStatuses>
                <ns1:downloadBulkJobStatuses>IN_PROGRESS</ns1:downloadBulkJobStatuses>
            </ns1:selector>
        </ns1:getBulkDownloadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [BulkDownloadStatusPage](../data/BulkDownloadStatusPage.md) | 対象の処理状況を含むコンテナです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>BulkService</ns1:service>
      <ns1:remainingQuota>129997</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>3.995</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownloadStatusResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>BulkDownloadStatusPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:downloadBulkJob>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:downloadBulkJobId>1</ns1:downloadBulkJobId>
            <ns1:downloadBulkUserName>8983-5689-9971-5970</ns1:downloadBulkUserName>
            <ns1:downloadBulkStartDate>2011-09-06T23:53:08+09:00</ns1:downloadBulkStartDate>
            <ns1:downloadBulkEndDate>2011-09-06T23:53:30+09:00</ns1:downloadBulkEndDate>
            <ns1:progress>100</ns1:progress>
            <ns1:downloadJobStatus>COMPLETED</ns1:downloadJobStatus>
            <ns1:downloadBulkDownloadUrl>https ://colo05.ss.yahooapis.jp/bulkDownload/V5.0/download/iHCYtsbwryBPGfYDAzEAyGSuINVilbjw5OSqHmYBL.n4ngH_NhxJ2TdmfsymSATBnVpaw.hHf1Bxv.g0YBr4uaUeXA--</ns1:downloadBulkDownloadUrl>
          </ns1:downloadBulkJob>
        </ns1:values>
      </ns1:rval>
    </ns1:getBulkDownloadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## getUploadUrl
#### リクエスト
一括アップロードのアップロード先URLを表します。

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 | 
##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
        <ns1:getUploadUrl>
            <ns1:accountId>00000001</ns1:accountId>
        </ns1:getUploadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [UploadUrlValue](../data/UploadUrlValue.md) | アップロードURLを格納するコンテナです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>BulkService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getUploadUrlResponse>
            <ns1:rval>
                <ns1:accountId>00000001</ns1:accountId>
                <ns1:acceptableUploadStatus>true</ns1:acceptableUploadStatus>
                <ns1:uploadUrl>https://sample.api.yahooapis.jp/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:uploadUrl>
            </ns1:rval>
        </ns1:getUploadUrlResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## getBulkUploadStatus
#### リクエスト
一括アップロードの処理状況を表します。

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| selector | ○ | [BulkUploadStatusSelector](../data/BulkUploadStatusSelector.md) | 処理状況を取得する条件を指定します。 | 
##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
        <ns1:getBulkUploadStatus>
            <ns1:selector>
                <ns1:accountId>00000001</ns1:accountId>
                <ns1:uploadBulkJobIds>12323230</ns1:uploadBulkJobIds>
                <ns1:uploadBulkJobStatuses>COMPLETED</ns1:uploadBulkJobStatuses> 
                <ns1:uploadBulkJobStatuses>IN_PROGRESS</ns1:uploadBulkJobStatuses> 
                <ns1:lang>EN</ns1:lang>
                <ns1:output>XML</ns1:output>
                <ns1:encoding>UTF-8</ns1:encoding>
            </ns1:selector>
        </ns1:getBulkUploadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```
#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [BulkUploadStatusPage](../data/BulkUploadStatusPage.md) | バルクアップロードの処理状況を含むコンテナです。 | 
##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>BulkService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkUploadStatusResponse>
            <ns1:rval>
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>BulkUploadStatusPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:uploadBulkJob>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:uploadBulkJobId>xxxxxxxxxx</ns1:uploadBulkJobId>
                        <ns1:uploadBulkUserName>xxxxxxxxxx</ns1:uploadBulkUserName>
                        <ns1:uploadBulkStartDate>2011-10-18T15:29:11+09:00</ns1:uploadBulkStartDate>
                        <ns1:uploadBulkEndDate>2011-10-18T15:29:20+09:00</ns1:uploadBulkEndDate>
                        <ns1:uploadBulkJobStatus>COMPLETED</ns1:uploadBulkJobStatus>
                        <ns1:processingItemsCount>
                        <ns1:campaignCount>0</ns1:campaignCount>
                        <ns1:negativeCampaignCriterionCount>0</ns1:negativeCampaignCriterionCount>
                        <ns1:adGroupCount>0</ns1:adGroupCount>
                        <ns1:negativeAdGroupCriterionCount>0</ns1:negativeAdGroupCriterionCount>
                        <ns1:biddableAdGroupCriterionCount>0</ns1:biddableAdGroupCriterionCount>
                        <ns1:adGroupAdCount>0</ns1:adGroupAdCount>
                        <ns1:campaignErrorCount>18</ns1:campaignErrorCount>
                        <ns1:negativeCampaignCriterionErrorCount>0</ns1:negativeCampaignCriterionErrorCount>
                        <ns1:adGroupErrorCount>0</ns1:adGroupErrorCount>
                        <ns1:negativeAdGroupCriterionErrorCount>0</ns1:negativeAdGroupCriterionErrorCount>
                        <ns1:biddableAdGroupCriterionErrorCount>0</ns1:biddableAdGroupCriterionErrorCount>
                        <ns1:adGroupAdErrorCount>0</ns1:adGroupAdErrorCount>
                        </ns1:processingItemsCount>
                        <ns1:progress>100</ns1:progress>
                        <ns1:bulkDownloadUrl></ns1:bulkDownloadUrl>
                    </ns1:uploadBulkJob>
                </ns1:values>
            </ns1:rval>
        </ns1:getBulkUploadStatusResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
