# PageFeedItemService
PageFeedItemServiceでは、ページフィードアイテムの取得、アップロード、一括取得を行います。

#### WSDL
| environment | url                                                                       |
|-------------|---------------------------------------------------------------------------|
| production  | https://ss.yahooapis.jp/services/V201808/PageFeedItemService?wsdl         |
| sandbox     | https://sandbox.ss.yahooapis.jp/services/V201808/PageFeedItemService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V201808/PageFeedItem

#### サービス概要
ページフィードアイテムの取得、アップロード、一括取得を行います。

#### 操作
PageFeedItemServiceで提供される操作を説明します。

+ [get](#get)
+ [getUploadUrl](#getuploadurl)
+ [upload](#upload)
+ [addDownloadJob](#adddownloadjob)
+ [getReviewSummary](#getreviewsummary)
+ [getJobStatus](#getjobstatus)
+ [download](#download)

#### オブジェクト
[PageFeedItem](../data/PageFeedItem)

## get
ページフィードアイテム情報を取得します。

#### リクエスト
| パラメータ    | 必須  | データ型                                                                 | 説明                         |
|----------|-----|----------------------------------------------------------------------|----------------------------|
| selector | ○   | [PageFeedItemSelector](../data/PageFeedItem/PageFeedItemSelector.md) | 取得するページフィードアイテムの情報を指定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>100000001</accountId>
        <feedFolderIds>1111</feedFolderIds>
        <feedFolderIds>2222</feedFolderIds>
        <feedFolderIds>3333</feedFolderIds>
        <approvalStatuses>APPROVED</approvalStatuses>
        <approvalStatuses>APPROVED_WITH_REVIEW</approvalStatuses>
        <approvalStatuses>POST_DISAPPROVED</approvalStatuses>
        <approvalStatuses>PRE_DISAPPROVED</approvalStatuses>
        <approvalStatuses>REVIEW</approvalStatuses>
        <pageFeedUrl>
          <text>yahoo</text>
          <matchType>BROAD</matchType>
        </pageFeedUrl>
        <pageFeedUrl>
          <text>co</text>
          <matchType>BROAD</matchType>
        </pageFeedUrl>
        <pageFeedUrl>
          <text>jp</text>
          <matchType>BROAD</matchType>
        </pageFeedUrl>
        <pageFeedCustomLabel>label1</pageFeedCustomLabel>
        <pageFeedCustomLabel>label2</pageFeedCustomLabel>
        <pageFeedCustomLabel>label3</pageFeedCustomLabel>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型                                                         | 説明                        |
|-------|--------------------------------------------------------------|---------------------------|
| rval  | [PageFeedItemPage](../data/PageFeedItem/PageFeedItemPage.md) | 取得されるページフィードアイテムのエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>PageFeedItem</ns2:service>
      <ns2:requestTime>1532511979524</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/PageFeedItem">
      <ns2:rval>
        <totalNumEntries>3</totalNumEntries>
        <Page.Type>PageFeedItem</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:pageFeedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>1111</ns2:feedFolderId>
            <ns2:pageFeedItemId>4444</ns2:pageFeedItemId>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:pageFeedUrl>https://www.yahoo.co.jp/</ns2:pageFeedUrl>
            <ns2:pageFeedCustomLabel>label1</ns2:pageFeedCustomLabel>
          </ns2:pageFeedItem>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:pageFeedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>2222</ns2:feedFolderId>
            <ns2:pageFeedItemId>4444</ns2:pageFeedItemId>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:pageFeedUrl>https://www.yahoo.co.jp/</ns2:pageFeedUrl>
            <ns2:pageFeedCustomLabel>label2</ns2:pageFeedCustomLabel>
          </ns2:pageFeedItem>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:pageFeedItem>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>3333</ns2:feedFolderId>
            <ns2:pageFeedItemId>4444</ns2:pageFeedItemId>
            <ns2:approvalStatus>APPROVED</ns2:approvalStatus>
            <ns2:pageFeedUrl>https://www.yahoo.co.jp/</ns2:pageFeedUrl>
            <ns2:pageFeedCustomLabel>label3</ns2:pageFeedCustomLabel>
          </ns2:pageFeedItem>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getUploadUrl
ページフィードのアップロード用URLを取得します。

#### リクエスト
| パラメータ      | 必須  | データ型                                                                                     | 説明                                |
|------------|-----|------------------------------------------------------------------------------------------|-----------------------------------|
| operations | ○   | [PageFeedItemUploadUrlOperation](../data/PageFeedItem/PageFeedItemUploadUrlOperation.md) | ページフィードをアップロードするフィードフォルダIDを指定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrl xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem">
      <operations>
        <accountId>100000001</accountId>
        <operand>
          <uploadType>NEW_OR_REPLACE</uploadType>
          <feedFolderId>900000001</feedFolderId>
        </operand>
        <operand>
          <uploadType>MODIFY</uploadType>
          <feedFolderId>800000001</feedFolderId>
        </operand>
      </operations>
    </getUploadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型                                                                           | 説明                                 |
|-------|--------------------------------------------------------------------------------|------------------------------------|
| rval  | [PageFeedItemUploadUrlPage](../data/PageFeedItem/PageFeedItemUploadUrlPage.md) | 取得されるページフィードアイテムのアップロードURLのエントリです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>PageFeedItem</ns2:service>
      <ns2:requestTime>1530861287731</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getUploadUrlResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/PageFeedItem">
      <ns2:rval>
        <totalNumEntries>2</totalNumEntries>
        <Page.Type>PageFeedItemUploadUrlPage</Page.Type>
        <ns2:values>
          <ns2:uploadUrl>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:uploadType>NEW_OR_REPLACE</ns2:uploadType>
            <ns2:feedFolderId>900000001</ns2:feedFolderId>
            <ns2:url>https://xxxxxxx.xxxxxxx.xxxx/22222</ns2:url>
          </ns2:uploadUrl>
        </ns2:values>
        <ns2:values>
          <ns2:uploadUrl>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:uploadType>MODIFY</ns2:uploadType>
            <ns2:feedFolderId>800000001</ns2:feedFolderId>
            <ns2:url>https://xxxxxxx.xxxxxxx.xxxx/11111</ns2:url>
          </ns2:uploadUrl>
        </ns2:values>
      </ns2:rval>
    </ns2:getUploadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## upload
getUploadUrlで取得したURLに対して、ページフィードアイテムのアップロード処理を実施します。

### レスポンス
##### ＜レスポンスサンプル＞
実行結果をJSON形式で返却します。

 ```
{
  "ResultSet" : {
    "Status" : 200,
    "Result" : [ {
      "operationSucceeded" : true,
      "pageFeedItemUploadJob" : {
        "accountId" : 1000000,
        "jobId" : 22,
        "uploadType" : "NEW_OR_REPLACE",
        "feedFolderId" : 33
      }
    } ]
  }
 ```

 ```
{
  "ResultSet": {
    "Error": [{
      "code": "211015",
      "message": "Same feedFolderId UploadJob is in progress."
    }]
  }
}
 ```


## addDownloadJob
登録されているページフィードアイテムを一括でダウンロードするためジョブを登録します。

#### リクエスト
| パラメータ      | 必須  | 値                                                                                            | 説明                        |
|------------|-----|----------------------------------------------------------------------------------------------|---------------------------|
| operations | ○   | [PageFeedItemDownloadJobOperation](../data/PageFeedItem/PageFeedItemDownloadJobOperation.md) | ダウンロードするページフィードの情報を設定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <addDownloadJob xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem">
      <operations>
        <accountId>100000001</accountId>
        <operand>
          <feedFolderIds>1111</feedFolderIds>
          <lang>JA</lang>
          <output>CSV</output>
          <encoding>UTF-8</encoding>
        </operand>
      </operations>
    </addDownloadJob>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型                                                                                             | 説明                          |
|-------|--------------------------------------------------------------------------------------------------|-----------------------------|
| rval  | [PageFeedItemDownloadJobReturnValue](../data/PageFeedItem/PageFeedItemDownloadJobReturnValue.md) | 操作結果を含むダウンロードに関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>PageFeedItem</ns2:service>
      <ns2:requestTime>1530861287810</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:addDownloadJobResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/PageFeedItem">
      <ns2:rval>
        <ListReturnValue.Type>PageFeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <ns2:job>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:jobId>1111</ns2:jobId>
            <ns2:feedFolderIds>1234</ns2:feedFolderIds>
            <ns2:progress>99</ns2:progress>
            <ns2:startDate>20170912131415</ns2:startDate>
            <ns2:endDate>20170913141516</ns2:endDate>
            <ns2:lang>JA</ns2:lang>
            <ns2:output>CSV</ns2:output>
            <ns2:encoding>SJIS</ns2:encoding>
            <ns2:downloadJobStatus>IN_PROGRESS</ns2:downloadJobStatus>
          </ns2:job>
        </ns2:values>
      </ns2:rval>
    </ns2:addDownloadJobResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReviewSummary
登録されているページフィードアイテムの審査成績・状況のサマリーを取得します。

### リクエスト
| パラメータ    | 必須  | 値                                                                                              | 説明                         |
|----------|-----|------------------------------------------------------------------------------------------------|----------------------------|
| selector | ○   | [PageFeedItemReviewSummarySelector](../data/PageFeedItem/PageFeedItemReviewSummarySelector.md) | 取得するページフィードアイテムの情報を指定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getReviewSummary xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>100000001</accountId>
        <feedFolderIds>1111</feedFolderIds>
        <feedFolderIds>2222</feedFolderIds>
        <feedFolderIds>3333</feedFolderIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </getReviewSummary>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型                                                                                   | 説明                               |
|-------|----------------------------------------------------------------------------------------|----------------------------------|
| rval  | [PageFeedItemReviewSummaryPage](../data/PageFeedItem/PageFeedItemReviewSummaryPage.md) | ページフィードアイテムの審査状況に関する情報のコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>PageFeedItem</ns2:service>
      <ns2:requestTime>1530861287779</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getReviewSummaryResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/PageFeedItem">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>PageFeedItemReviewSummaryPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reviewSummary>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:feedFolderId>1000</ns2:feedFolderId>
            <ns2:entityCount>100</ns2:entityCount>
            <ns2:approvedCount>100</ns2:approvedCount>
            <ns2:approvedWithReviewCount>100</ns2:approvedWithReviewCount>
            <ns2:reviewCount>100</ns2:reviewCount>
            <ns2:preDisapprovedCount>100</ns2:preDisapprovedCount>
            <ns2:postDisapprovedCount>100</ns2:postDisapprovedCount>
          </ns2:reviewSummary>
        </ns2:values>
      </ns2:rval>
    </ns2:getReviewSummaryResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getJobStatus
upload、downloadの処理状況を取得します。downloadJobStatusがCOMPLETEDの場合、レスポンスにダウンロードURLが設定されます。

### リクエスト
| パラメータ    | 必須  | 値                                                                                      | 説明                            |
|----------|-----|----------------------------------------------------------------------------------------|-------------------------------|
| selector | ○   | [PageFeedItemJobStatusSelector](../data/PageFeedItem/PageFeedItemJobStatusSelector.md) | 処理状況を取得するページフィードアイテム情報を設定します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getJobStatus xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <selector>
        <accountId>100000001</accountId>
        <jobIds>1111</jobIds>
        <jobIds>2222</jobIds>
        <jobIds>3333</jobIds>
        <jobType>UPLOAD</jobType>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </getJobStatus>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型                                                                           | 説明                 |
|-------|--------------------------------------------------------------------------------|--------------------|
| rval  | [PageFeedItemJobStatusPage](../data/PageFeedItem/PageFeedItemJobStatusPage.md) | 登録済の処理状況に関する内容です。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201808/PageFeedItem" xmlns:ns2="http://ss.yahooapis.jp/V201808">
      <ns2:service>PageFeedItem</ns2:service>
      <ns2:requestTime>1530861287752</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getJobStatusResponse xmlns="http://ss.yahooapis.jp/V201808" xmlns:ns2="http://ss.yahooapis.jp/V201808/PageFeedItem">
      <ns2:rval>
        <totalNumEntries>2</totalNumEntries>
        <Page.Type>PageFeedItemJobStatusPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PageFeedItemDownloadJob">
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:jobId>1111</ns2:jobId>
            <ns2:feedFolderIds>1234</ns2:feedFolderIds>
            <ns2:progress>99</ns2:progress>
            <ns2:startDate>20170912131415</ns2:startDate>
            <ns2:endDate>20170913141516</ns2:endDate>
            <ns2:lang>JA</ns2:lang>
            <ns2:output>CSV</ns2:output>
            <ns2:encoding>SJIS</ns2:encoding>
            <ns2:downloadJobStatus>COMPLETED</ns2:downloadJobStatus>
            <ns2:downloadUrl>https://xxxxxxx/xxxxxxxxx</ns2:downloadUrl>
          </ns2:job>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PageFeedItemDownloadJob">
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:jobId>2222</ns2:jobId>
            <ns2:feedFolderIds>1234</ns2:feedFolderIds>
            <ns2:progress>99</ns2:progress>
            <ns2:startDate>20170912131415</ns2:startDate>
            <ns2:endDate>20170913141516</ns2:endDate>
            <ns2:lang>JA</ns2:lang>
            <ns2:output>CSV</ns2:output>
            <ns2:encoding>SJIS</ns2:encoding>
            <ns2:downloadJobStatus>IN_PROGRESS</ns2:downloadJobStatus>
          </ns2:job>
        </ns2:values>
      </ns2:rval>
    </ns2:getJobStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
