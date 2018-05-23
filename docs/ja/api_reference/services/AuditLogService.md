# AuditLogService
AuditLogServiceは、操作履歴のダウンロード機能を提供します。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V201805/AuditLogService?wsdl |
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V201805/AuditLogService?wsdl |

#### Namespace
http://ss.yahooapis.jp/V201805/AuditLog

#### サービス概要
操作履歴のダウンロード機能を提供します。

#### 操作
AuditLogServiceで提供される操作を説明します。

+ [get](#get)
+ [addJob](#addjob)
+ [download](#download)

#### オブジェクト
[AuditLog](../data/AuditLog)

## get

### リクエスト
操作履歴のダウンロードURLを取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AuditLogSelector](../data/AuditLog/AuditLogSelector.md) | 登録したジョブを照会する検索条件を保持するオブジェクトです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AuditLog" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://ss.yahooapis.jp/V201805/AuditLog" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <selector>
        <accountId>100000001</accountId>
        <jobIds>1111</jobIds>
        <jobIds>1112</jobIds>
        <jobStatuses>SYSTEM_ERROR</jobStatuses>
        <jobStatuses>COMPLETED</jobStatuses>
        <jobStatuses>IN_PROGRESS</jobStatuses>
        <jobStatuses>TIMEOUT</jobStatuses>
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
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [AuditLogPage](../data/AuditLog/AuditLogPage.md) | getメソッドの実行結果を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AuditLog" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AuditLog</ns2:service>
      <ns2:requestTime>1523506330233</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AuditLog">
      <ns2:rval>
        <totalNumEntries>4</totalNumEntries>
        <Page.Type>AuditLogPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:jobId>19771824</ns2:jobId>
            <ns2:jobName>Sample Audit Log</ns2:jobName>
            <ns2:jobStatus>IN_PROGRESS</ns2:jobStatus>
            <ns2:eventSelector>
              <ns2:entityType>ALL</ns2:entityType>
              <ns2:eventTypes>ADD</ns2:eventTypes>
              <ns2:eventTypes>SET</ns2:eventTypes>
              <ns2:eventTypes>REMOVE</ns2:eventTypes>
            </ns2:eventSelector>
            <ns2:dateRange>
              <ns2:startDate>20170701000000</ns2:startDate>
              <ns2:endDate>20170810235959</ns2:endDate>
            </ns2:dateRange>
            <ns2:sourceType>ALL</ns2:sourceType>
            <ns2:output>CSV</ns2:output>
            <ns2:encoding>UTF_8</ns2:encoding>
            <ns2:lang>JA</ns2:lang>
          </ns2:job>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:jobId>222222</ns2:jobId>
            <ns2:jobName>Sample Audit Log2</ns2:jobName>
            <ns2:jobStatus>COMPLETED</ns2:jobStatus>
            <ns2:downloadUrl>https ://colo01.ss.yahooapis.jp/audit/V201805/download/XtuXVU2EbFtOg4qiJCos2FRMXLWTmulJXr4D9Ed1HVLBFrf2Wp3qHwgrVcswR65IHc7bJYsluuJqfGLdDsChrAh_mFtx.2OJlcFkpJ8vgEgygk3dnz6IFW376asnE9kK_z8zhFiL0hx7Tf7UhwtvPw0bYD_vt9Zy2vLBLkNRTeEjU0OrR4ydUg3PvPpg0nDXzbwH2B3xD37Qx.PN6_2tCKpvz5m8kWZOtudS2oeGJAYh95gcBF2Ng0Mi4ZlJoGmRcDNsq79eTW7lsSFj8q7ZT1benaYFE.KsJigCSNPJI0SyLc_neR6PR0t3cov3kNURju6CQY_FLXos45900v6jpAhqZg--</ns2:downloadUrl>
            <ns2:eventSelector>
              <ns2:entityType>ALL</ns2:entityType>
              <ns2:eventTypes>ADD</ns2:eventTypes>
              <ns2:eventTypes>SET</ns2:eventTypes>
              <ns2:eventTypes>REMOVE</ns2:eventTypes>
            </ns2:eventSelector>
            <ns2:dateRange>
              <ns2:startDate>20170701000000</ns2:startDate>
              <ns2:endDate>20170810235959</ns2:endDate>
            </ns2:dateRange>
            <ns2:sourceType>ALL</ns2:sourceType>
            <ns2:output>CSV</ns2:output>
            <ns2:encoding>UTF_8</ns2:encoding>
            <ns2:lang>JA</ns2:lang>
          </ns2:job>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## addJob

### リクエスト
操作履歴ファイルをダウンロードするためのジョブを登録します。<br>

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [AuditLogJobOperation](../data/AuditLog/AuditLogJobOperation.md) | 登録対象のジョブを保持するオブジェクトです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://ss.yahooapis.jp/V201805/AuditLog" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <addJob xmlns="http://ss.yahooapis.jp/V201805/AuditLog">
      <operations>
        <accountId>111111</accountId>
        <operand>
          <jobName>Sample Audit Log</jobName>
          <eventSelector>
            <entityType>ALL</entityType>
            <eventTypes>ADD</eventTypes>
            <eventTypes>SET</eventTypes>
            <eventTypes>REMOVE</eventTypes>
          </eventSelector>
          <dateRange>
            <startDate>20170701000000</startDate>
            <endDate>20170810235959</endDate>
          </dateRange>
          <sourceType>ALL</sourceType>
          <output>CSV</output>
          <encoding>UTF_8</encoding>
          <lang>JA</lang>
        </operand>
      </operations>
    </addJob>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [AuditLogReturnValue](../data/AuditLog/AuditLogReturnValue.md) | addJobメソッドの実行結果を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://ss.yahooapis.jp/V201805/AuditLog" xmlns:ns2="http://ss.yahooapis.jp/V201805">
      <ns2:service>AuditLog</ns2:service>
      <ns2:requestTime>1523506330256</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:addJobResponse xmlns="http://ss.yahooapis.jp/V201805" xmlns:ns2="http://ss.yahooapis.jp/V201805/AuditLog">
      <ns2:rval>
        <ListReturnValue.Type>AuditLogReturnValue</ListReturnValue.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:job>
            <ns2:accountId>111111</ns2:accountId>
            <ns2:jobId>19771824</ns2:jobId>
            <ns2:jobName>Sample Audit Log</ns2:jobName>
            <ns2:jobStatus>IN_PROGRESS</ns2:jobStatus>
            <ns2:eventSelector>
              <ns2:entityType>ALL</ns2:entityType>
              <ns2:eventTypes>ADD</ns2:eventTypes>
              <ns2:eventTypes>SET</ns2:eventTypes>
              <ns2:eventTypes>REMOVE</ns2:eventTypes>
            </ns2:eventSelector>
            <ns2:dateRange>
              <ns2:startDate>20170701000000</ns2:startDate>
              <ns2:endDate>20170810235959</ns2:endDate>
            </ns2:dateRange>
            <ns2:sourceType>ALL</ns2:sourceType>
            <ns2:output>CSV</ns2:output>
            <ns2:encoding>UTF_8</ns2:encoding>
            <ns2:lang>JA</ns2:lang>
          </ns2:job>
        </ns2:values>
      </ns2:rval>
    </ns2:addJobResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## download

### リクエスト
getで取得したURLから、操作履歴ファイルをダウンロードします。<br>





<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
