# Creating/Retrieving Sponsored Search Report Report (Ver.6.0-)
## What is “Performance Report”?
Performance Report is a function of confirming performance in Campaign, Ad Group, Ad, Keyword, etc.   
To display report, creation of report and template will be required.    
Customizing report is possible, like setting hierarchy of performance, item display, summary period, etc.  
  
Report functions supported in Campaign Management Tool are also available from API.  

## How to operate from Sponsored Search API
To display the performance report, use the two services below from Sponsored Search API.  

##### 1.	ReportDefinitionService   
ReportDefinitionService can retrieve and add/update/delete the report definition.   
In report definition, field have to be designate.  

##### 2.	ReportService  
ReportService can retrieve and add/delete the report.  
It also can retrieve the Download URL of report.  

## Scenerio Sample
This is a process of create and delete of report template and actual report, to retrieve Performance Report, 
using Sponsored Search API.  

#### 1.	Retrieve Field of Template
Use getReportFields of ReportDefinitionService.  
Retrieve list of available report fields by designated ReportType.  
Each report fields encapsulate the field name, field data type, and enumerations.

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <soapenv:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
    </ns1:RequestHeader>
  </soapenv:Header>
  <soapenv:Body>
    <ns1:getReportFields>
      <ns1:reportType>LANDING_PAGE_URL</ns1:reportType>
    </ns1:getReportFields>
  </soapenv:Body>
</soapenv:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportDefinitionService</ns1:service>
      <ns1:remainingQuota>4997</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.1508</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getReportFieldsResponse>
      <ns1:rval>
        <ns1:operationSucceeded>true</ns1:operationSucceeded>
        <ns1:fields>
          <ns1:fieldName>AVERAGECPC</ns1:fieldName>
          <ns1:displayFieldNameJA>平均CPC</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Avg. CPC</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>averageCpc</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>AVERAGECPM</ns1:fieldName>
          <ns1:displayFieldNameJA>平均CPM</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Avg. CPM</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>averageCpm</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>AVERAGEPOSITION</ns1:fieldName>
          <ns1:displayFieldNameJA>平均掲載順位</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Avg. Position</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>averagePosition</ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>CLICKS</ns1:fieldName>
          <ns1:displayFieldNameJA>クリック数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Clicks</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>clicks</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>UNIQUECONVERSIONRATE</ns1:fieldName>
          <ns1:displayFieldNameJA>ユニークコンバージョン率</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Unique Conversion Rate</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>uniqueConversionRate</ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>TOTALCONVERSIONRATE</ns1:fieldName>
          <ns1:displayFieldNameJA>総コンバージョン率</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Total Conversion Rate</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>totalConversionRate</ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>UNIQUECONVERSIONS</ns1:fieldName>
          <ns1:displayFieldNameJA>コスト/ユニークコンバージョン数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Unique Conversions</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>uniqueConversions</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>TOTALCONVERSIONS</ns1:fieldName>
          <ns1:displayFieldNameJA>コスト/総コンバージョン数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Total Conversions</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>totalConversions</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>TOTALREVENUE</ns1:fieldName>
          <ns1:displayFieldNameJA>合計売上金額</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Total Revenue</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>totalRevenue</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>COST</ns1:fieldName>
          <ns1:displayFieldNameJA>コスト</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Cost</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>cost</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>COSTUNIQUECONVERSIONS</ns1:fieldName>
          <ns1:displayFieldNameJA>コスト/ユニークコンバージョン数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Cost / Unique Conversions
          </ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>costUniqueConversions</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>COSTTOTALCONVERSIONS</ns1:fieldName>
          <ns1:displayFieldNameJA>コスト/総コンバージョン数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Cost / Total Conversions
          </ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>CTR</ns1:fieldName>
          <ns1:displayFieldNameJA>クリック率</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>CTR</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>ctr</ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>IMPRESSIONS</ns1:fieldName>
          <ns1:displayFieldNameJA>インプレッション数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Impressions</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>INVALIDCLICKRATE</ns1:fieldName>
          <ns1:displayFieldNameJA>無効なクリック率</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Invalid Click Rate</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>invalidClickRate</ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>INVALIDCLICKS</ns1:fieldName>
          <ns1:displayFieldNameJA>無効なクリック</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Invalid Clicks</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>invalidClicks</ns1:xmlAttributeName>
          <ns1:fieldType>Long</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>REVENUEUNIQUECONVERSIONS</ns1:fieldName>
          <ns1:displayFieldNameJA>売上/ユニークコンバージョン数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Revenue / Unique Conversions
          </ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>revenueUniqueConversions
          </ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>REVENUETOTALCONVERSIONS</ns1:fieldName>
          <ns1:displayFieldNameJA>売上/総コンバージョン数</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Revenue / Total Conversions
          </ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>revenueTotalConversions
          </ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>EXACTMATCHIMPRESSIONSHARE</ns1:fieldName>
          <ns1:displayFieldNameJA>完全一致のインプレッションシェア</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Exact Match Impression Share
          </ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>exactMatchImpressionShare
          </ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>BUDGETLOSTIMPRESSIONSHARE</ns1:fieldName>
          <ns1:displayFieldNameJA>インプレッション損失率（予算）</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Budget Lost Impression Share
          </ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>budgetLostImpressionShare
          </ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>IMPRESSIONSHARE</ns1:fieldName>
          <ns1:displayFieldNameJA>インプレッションシェア</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Impression Share</ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>impressionShare</ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
        <ns1:fields>
          <ns1:fieldName>QUALITYLOSTIMPRESSIONSHARE</ns1:fieldName>
          <ns1:displayFieldNameJA>インプレッション損失率（掲載順位）</ns1:displayFieldNameJA>
          <ns1:displayFieldNameEN>Quality Lost ImpressionShare
          </ns1:displayFieldNameEN>
          <ns1:xmlAttributeName>qualityLostImpressionShare
          </ns1:xmlAttributeName>
          <ns1:fieldType>Double</ns1:fieldType>
          <ns1:canSelect>true</ns1:canSelect>
          <ns1:canFilter>true</ns1:canFilter>
        </ns1:fields>
      </ns1:rval>
    </ns1:getReportFieldsResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 2.	Create Report Template
Use mutat:add of ReportDefinitionService.  
Creates the report template.
It requires the following:  
* Name of report definition
* Designating summary period
* Designating creation time (Frequency)
* Japanese/English selection
* Designating output format

##### Request Sample
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
          <ns1:reportName>Sample LANDING_PAGE_URL Report</ns1:reportName>
          <ns1:reportType>LANDING_PAGE_URL</ns1:reportType>
          <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
          <ns1:dateRange>
            <ns1:startDate>20160101</ns1:startDate>
            <ns1:endDate>20161231</ns1:endDate>
          </ns1:dateRange>
          <ns1:fields>CAMPAIGN_ID</ns1:fields>
          <ns1:fields>ADGROUP_ID</ns1:fields>
          <ns1:fields>CAMPAIGN_NAME</ns1:fields>
          <ns1:fields>ADGROUP_NAME</ns1:fields>
          <ns1:fields>COST</ns1:fields>
          <ns1:fields>IMPS</ns1:fields>
          <ns1:fields>CLICKS</ns1:fields>
          <ns1:fields>CLICK_RATE</ns1:fields>
          <ns1:fields>AVG_CPM</ns1:fields>
          <ns1:fields>AVG_CPC</ns1:fields>
          <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
          <ns1:fields>REVENUE</ns1:fields>
          <ns1:fields>UNIQUE_CONVERSION</ns1:fields>
          <ns1:fields>UNIQUE_CONVERSION_RATE</ns1:fields>
          <ns1:fields>REVENUE_UNIQUE_CONVERSION</ns1:fields>
          <ns1:fields>TRACKING_URL</ns1:fields>
          <ns1:fields>CUSTOM_PARAMETERS</ns1:fields>
          <ns1:fields>LANDING_PAGE_URL</ns1:fields>
          <ns1:fields>NETWORK</ns1:fields>
          <ns1:fields>DEVICE</ns1:fields>
          <ns1:fields>DAY</ns1:fields>
          <ns1:fields>DAY_OF_WEEK</ns1:fields>
          <ns1:fields>QUARTER</ns1:fields>
          <ns1:fields>YEAR</ns1:fields>
          <ns1:fields>MONTH</ns1:fields>
          <ns1:fields>MONTH_OF_YEAR</ns1:fields>
          <ns1:fields>WEEK</ns1:fields>
          <ns1:fields>OBJECT_OF_CONVERSION_TRACKING</ns1:fields>
          <ns1:fields>CONVERSION_NAME</ns1:fields>
          <ns1:sortFields>
            <ns1:type>ASC</ns1:type>
            <ns1:field>CLICKS</ns1:field>
          </ns1:sortFields>
          <ns1:filters>
            <ns1:field>TRACKING_URL</ns1:field>
            <ns1:operator>IN</ns1:operator>
            <ns1:value>http://yahoo.co.jp</ns1:value>
            <ns1:value>http://marketing.yahoo.co.jp</ns1:value>
            <ns1:value>http://promotionalads.yahoo.co.jp</ns1:value>
          </ns1:filters>
          <ns1:filters>
            <ns1:field>IMPS</ns1:field>
            <ns1:operator>GREATER_THAN</ns1:operator>
            <ns1:value>0</ns1:value>
          </ns1:filters>
          <ns1:filters>
            <ns1:field>CAMPAIGN_ID</ns1:field>
            <ns1:operator>IN</ns1:operator>
            <ns1:value>200000001</ns1:value>
            <ns1:value>200000002</ns1:value>
            <ns1:value>200000003</ns1:value>
            <ns1:value>200000003</ns1:value>
            <ns1:value>200000004</ns1:value>
            <ns1:value>200000005</ns1:value>
          </ns1:filters>
          <ns1:isTemplate>FALSE</ns1:isTemplate>
          <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
          <ns1:specifyDay>28</ns1:specifyDay>
          <ns1:format>CSV</ns1:format>
          <ns1:encode>UTF-8</ns1:encode>
          <ns1:language>EN</ns1:language>
          <ns1:compress>NONE</ns1:compress>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </soapenv:Body>
</soapenv:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportDefinitionService</ns1:service>
      <ns1:remainingQuota>993</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.7982</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportDefinition>
            <ns1:reportId>100000001</ns1:reportId>
            <ns1:reportName>Sample LANDING_PAGE_URL Report</ns1:reportName>
            <ns1:reportType>LANDING_PAGE_URL</ns1:reportType>
            <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
            <ns1:dateRange>
              <ns1:startDate>20160101</ns1:startDate>
              <ns1:endDate>20161231</ns1:endDate>
            </ns1:dateRange>
            <ns1:fields>CAMPAIGN_ID</ns1:fields>
            <ns1:fields>ADGROUP_ID</ns1:fields>
            <ns1:fields>CAMPAIGN_NAME</ns1:fields>
            <ns1:fields>ADGROUP_NAME</ns1:fields>
            <ns1:fields>COST</ns1:fields>
            <ns1:fields>IMPS</ns1:fields>
            <ns1:fields>CLICKS</ns1:fields>
            <ns1:fields>CLICK_RATE</ns1:fields>
            <ns1:fields>AVG_CPM</ns1:fields>
            <ns1:fields>AVG_CPC</ns1:fields>
            <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
            <ns1:fields>REVENUE</ns1:fields>
            <ns1:fields>UNIQUE_CONVERSION</ns1:fields>
            <ns1:fields>UNIQUE_CONVERSION_RATE</ns1:fields>
            <ns1:fields>REVENUE_UNIQUE_CONVERSION</ns1:fields>
            <ns1:fields>TRACKING_URL</ns1:fields>
            <ns1:fields>CUSTOM_PARAMETERS</ns1:fields>
            <ns1:fields>LANDING_PAGE_URL</ns1:fields>
            <ns1:fields>NETWORK</ns1:fields>
            <ns1:fields>DEVICE</ns1:fields>
            <ns1:fields>DAY</ns1:fields>
            <ns1:fields>DAY_OF_WEEK</ns1:fields>
            <ns1:fields>QUARTER</ns1:fields>
            <ns1:fields>YEAR</ns1:fields>
            <ns1:fields>MONTH</ns1:fields>
            <ns1:fields>MONTH_OF_YEAR</ns1:fields>
            <ns1:fields>WEEK</ns1:fields>
            <ns1:fields>OBJECT_OF_CONVERSION_TRACKING</ns1:fields>
            <ns1:fields>CONVERSION_NAME</ns1:fields>
            <ns1:sortFields>
              <ns1:type>ASC</ns1:type>
              <ns1:field>CLICKS</ns1:field>
            </ns1:sortFields>
            <ns1:filters>
              <ns1:field>TRACKING_URL</ns1:field>
              <ns1:operator>IN</ns1:operator>
              <ns1:value>http://yahoo.co.jp</ns1:value>
              <ns1:value>http://marketing.yahoo.co.jp</ns1:value>
              <ns1:value>http://promotionalads.yahoo.co.jp</ns1:value>
            </ns1:filters>
            <ns1:filters>
              <ns1:field>IMPS</ns1:field>
              <ns1:operator>GREATER_THAN</ns1:operator>
              <ns1:value>0</ns1:value>
            </ns1:filters>
            <ns1:filters>
              <ns1:field>CAMPAIGN_ID</ns1:field>
              <ns1:operator>IN</ns1:operator>
              <ns1:value>200000001</ns1:value>
              <ns1:value>200000002</ns1:value>
              <ns1:value>200000003</ns1:value>
              <ns1:value>200000003</ns1:value>
              <ns1:value>200000004</ns1:value>
              <ns1:value>200000005</ns1:value>
            </ns1:filters>
            <ns1:isTemplate>FALSE</ns1:isTemplate>
            <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
            <ns1:specifyDay>28</ns1:specifyDay>
            <ns1:format>CSV</ns1:format>
            <ns1:encode>UTF-8</ns1:encode>
            <ns1:language>EN</ns1:language>
            <ns1:compress>NONE</ns1:compress>
          </ns1:reportDefinition>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 3.	Create Report
Use mutate:add of ReportService.  
Creates report from designated ReportID.<br>
*This process is not necessary for Scheduled Report.  

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:reportId>10000000001</ns1:reportId>
        </ns1:operand>
        <ns1:operand>
          <ns1:reportId>10000000002</ns1:reportId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportRecord>
            <ns1:accountId>10000000001</ns1:accountId>
            <ns1:reportId>10000000001</ns1:reportId>
            <ns1:reportJobId>200000001</ns1:reportJobId>
            <ns1:reportJobStatus>WAIT</ns1:reportJobStatus>
            <ns1:requestTime>2011/11/30 23:22:30</ns1:requestTime>
          </ns1:reportRecord>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 4.	Confirm the Report Status
Use get of ReportService.  
Can confirm the report creation status. <br>
Also, download URL will be displayed after the report is created.

##### Request Sample
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
        <ns1:accountId>100000000</ns1:accountId>
        <ns1:reportIds>100000003</ns1:reportIds>
        <ns1:reportIds>100000007</ns1:reportIds>
        <ns1:reportIds>100000005</ns1:reportIds>
        <ns1:reportJobIds>100000003</ns1:reportJobIds>
        <ns1:reportJobIds>100000007</ns1:reportJobIds>
        <ns1:reportJobIds>100000005</ns1:reportJobIds>
        <ns1:reportTypes>AD_CUSTOMIZERS</ns1:reportTypes>
        <ns1:reportTypes>TARGET_LIST</ns1:reportTypes>
        <ns1:reportTypes>LANDING_PAGE_URL</ns1:reportTypes>
        <ns1:reportJobStatuses>WAIT</ns1:reportJobStatuses>
        <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
        <ns1:reportJobStatuses>IN_PROGRESS</ns1:reportJobStatuses>
        <ns1:reportJobStatuses>FAILED</ns1:reportJobStatuses>
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>10</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>4</ns1:totalNumEntries>
        <ns1:Page.Type>ReportPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportRecord>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportId>2000000001</ns1:reportId>
            <ns1:reportJobId>3000000001</ns1:reportJobId>
            <ns1:reportJobStatus>COMPLETED</ns1:reportJobStatus>
            <ns1:requestTime>2015/11/30 22:22:30</ns1:requestTime>
            <ns1:completeTime>2015/11/30 23:22:30</ns1:completeTime>
            <ns1:reportDownloadURL>https://ss.yahooapis.jp/report/V6.0/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:reportDownloadURL>
          </ns1:reportRecord>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportRecord>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportId>2000000002</ns1:reportId>
            <ns1:reportJobId>3000000002</ns1:reportJobId>
            <ns1:reportJobStatus>FAILED</ns1:reportJobStatus>
            <ns1:reportJobErrorDetail>INTERNAL_ERROR</ns1:reportJobErrorDetail>
            <ns1:requestTime>2015/11/30 22:22:30</ns1:requestTime>
          </ns1:reportRecord>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportRecord>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportId>2000000003</ns1:reportId>
            <ns1:reportJobId>3000000003</ns1:reportJobId>
            <ns1:reportJobStatus>IN_PROGRESS</ns1:reportJobStatus>
            <ns1:requestTime>2015/11/30 22:22:30</ns1:requestTime>
          </ns1:reportRecord>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportRecord>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportId>2000000004</ns1:reportId>
            <ns1:reportJobId>3000000004</ns1:reportJobId>
            <ns1:reportJobStatus>WAIT</ns1:reportJobStatus>
            <ns1:requestTime>2015/11/30 22:22:30</ns1:requestTime>
          </ns1:reportRecord>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 5.	Delete Report
Use mutate:remove of ReportService.  
Deletes downloaded report from ReportList.  

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>REMOVE</ns1:operator>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:reportJobId>10000000001</ns1:reportJobId>
        </ns1:operand>
        <ns1:operand>
          <ns1:reportJobId>10000000002</ns1:reportJobId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportRecord>
            <ns1:reportJobId>200000001</ns1:reportJobId>
          </ns1:reportRecord>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportRecord>
            <ns1:reportJobId>200000002</ns1:reportJobId>
          </ns1:reportRecord>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 6.	Delete Report Template
Uses mutate:remove of ReportDefinitionService.  
Deletes the unnecessary defined report.  

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
      <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>REMOVE</ns1:operator>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:reportId>123456789</ns1:reportId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportDefinitionService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportDefinition>
            <ns1:reportId>123456789</ns1:reportId>
          </ns1:reportDefinition>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
