# ReportService
ReportServiceでは、レポートの取得および作成・削除を行います。<br>
また、レポートのダウンロードURLを取得する操作が提供されます。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/ReportService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/ReportService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V201805/Report

#### サービス概要
以下の操作が実行可能です。
- レポートの取得
- レポートの登録
- レポートの削除

【レポートダウンロードジョブの登録上限数】
- ONETIMEレポート（Add Template指定：NO）として登録されたレポートダウンロードジョブは、標準認証と代行認証それぞれで最大60件まで登録できます(ReportJobStatus：COMPLETED又はFAILEDは除く)。
- 定期レポート（Add Template指定：YES）として登録されたレポートダウンロードジョブの登録上限数はありません。<br>
※登録上限数に達した状態から新たにダウンロードジョブを登録する場合は、登録済みのダウンロードジョブを削除する必要があります。<br>

【注意事項】
- レポートのダウンロードは、getメソッドで取得したURLから行います。<br>
URLが有効な期間は、ステータスがCOMPLETEDになってから5分間です。
- レポートダウンロードジョブは、リクエストしてから1週間（7日間）で自動的に削除されます。


#### 操作
ReportServiceで提供される操作を説明します。

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)

#### オブジェクト
[Report](../data/Report)

## get
レポートに関する情報を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [ReportSelector](../data/Report/ReportSelector.md) | 操作の対象とするレポートです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>100000001</accountId>
        <reportIds>1111</reportIds>
        <reportIds>1112</reportIds>
        <reportTypes>ACCOUNT</reportTypes>
        <reportTypes>CAMPAIGN</reportTypes>
        <reportTypes>ADGROUP</reportTypes>
        <reportTypes>AD</reportTypes>
        <reportTypes>KEYWORDS</reportTypes>
        <reportTypes>SEARCH_QUERY</reportTypes>
        <reportTypes>GEO</reportTypes>
        <reportTypes>FEED_ITEM</reportTypes>
        <reportTypes>GEO_TARGET</reportTypes>
        <reportTypes>SCHEDULE_TARGET</reportTypes>
        <reportTypes>BID_STRATEGY</reportTypes>
        <reportTypes>AD_CUSTOMIZERS</reportTypes>
        <reportTypes>TARGET_LIST</reportTypes>
        <reportTypes>LANDING_PAGE_URL</reportTypes>
        <reportJobStatuses>WAIT</reportJobStatuses>
        <reportJobStatuses>COMPLETED</reportJobStatuses>
        <reportJobStatuses>IN_PROGRESS</reportJobStatuses>
        <reportJobStatuses>FAILED</reportJobStatuses>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [ReportPage](../data/Report/ReportPage.md) | 取得されるレポートのエントリーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1523506336415</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Report">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <Page.Type>ReportPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1111</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
            <ns2:completeTime>2017/11/27 14:33:20</ns2:completeTime>
            <ns2:reportDownloadURL>https://ss.yahooapis.jp/report/V201805/download/3CRAGObSahcIylBoDZS5ftx7qS4VM5jSHqs77QZqmpBFnJFP2jvKe3Dy72UEX3InsUoShWXa3YcX3AmbtqxGco6B</ns2:reportDownloadURL>
          </ns2:reportRecord>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1112</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report2</ns2:reportName>
            <ns2:reportJobStatus>FAILED</ns2:reportJobStatus>
            <ns2:reportJobErrorDetail>INTERNAL_ERROR</ns2:reportJobErrorDetail>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1113</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report3</ns2:reportName>
            <ns2:reportJobStatus>IN_PROGRESS</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1114</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report3</ns2:reportName>
            <ns2:reportJobStatus>WAIT</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
レポートを作成します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [ReportOperation](../data/Report/ReportOperation.md) | 操作の対象となるレポートおよび操作の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/Report">
      <operations>
        <operator>ADD</operator>
        <accountId>11111</accountId>
        <operand>
          <reportId>2222</reportId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | 操作結果を含むレポートのコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1523506336428</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Report">
      <ns2:rval>
        <ListReturnValue.Type>ReportReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>1113</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report3</ns2:reportName>
            <ns2:reportJobStatus>IN_PROGRESS</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
レポートを削除します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [ReportOperation](../data/Report/ReportOperation.md) | 操作の対象となるレポートおよび操作の内容を表します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://ss.yahooapis.jp/V201805/Report">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <reportId>2222</reportId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | 操作結果を含むレポートのコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/Report" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1523506336443</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/Report">
      <ns2:rval>
        <ListReturnValue.Type>ReportReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>11111</ns2:accountId>
            <ns2:reportId>2222</ns2:reportId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:requestTime>2017/11/27 14:32:48</ns2:requestTime>
            <ns2:completeTime>2017/11/27 14:33:20</ns2:completeTime>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
