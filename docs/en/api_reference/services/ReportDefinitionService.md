# ReportDefinitionService
ReportDefinitionService is to get, add, update, or delete report definition. <br>
Report defines report type, date range, and fields. <br>
It also provides operation to get available report fields for specific report type.
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V5.2/ReportDefinitionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V5.2/ReportDefinitionService?wsdl |
#### Namespace
http://ss.yahooapis.jp/V5
#### Overview
Get, update, or delete report definitions. Report definitions can be saved up to 30 as templates. <br>
If not saved as template, there is no limit in setting definition.<br>
<br>
[Important Notes]<br>
No data will be shown in the report of search_query, destination_url and geo, when there is no performance data.<br>
Also, if you specify the report segment in any other report type, zero performance data will not be shown either.<br>
<br>
Report definition can be confirmed only by the authentic method when the report definition was created.<br>
- If it was created by authentication: Cannot confirm by on behalf of access.<br>
- If it was created by on behalf of access: Cannot confirm by authentication.<br>
The maximum template number is the sum total of the report definition created by each authentic method.<br>
For example, if you've already saved 20 definitions by authentication, you will be able to save 10 more by on behalf of access. <br>
So if you need to add report definition over the limit, you will need to delete either definition.

#### Operation
Explains the operations provided by ReportDefinitionService.
## get
### Request
Get information related to report definition.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [ReportDefinitionSelector](../data/ReportDefinitionSelector.md) | Report definition relate to the operations to apply. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountID>xxxxxxxxxxxxxxxxxx</ns1:apiAccountID>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000001</ns1:accountId>
                <ns1:reportIds>11522</ns1:reportIds>
                <ns1:reportIds>100000003</ns1:reportIds>
                <ns1:paging>	
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionPage](../data/ReportDefinitionPage.md) | A list of report definitions. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>ReportDefinitionService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>1</ns1:totalNumEntries>
            <ns1:Page.Type>ReportDefinitionPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>10000000003</ns1:reportId>
                  <ns1:accountId>200000001</ns1:accountId>
                  <ns1:reportName>test</ns1:reportName>
                  <ns1:reportType>ACCOUNT</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20110301</ns1:startDate>
                     <ns1:endDate>20111011</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:filters>
                     <ns1:field>cpc</ns1:field>
                     <ns1:operator>GREATER_THAN_EQUALS</ns1:operator>
                     <ns1:values>100</ns1:values>
                  </ns1:filters>
                  <ns1:filters>
                     <ns1:field>pv</ns1:field>
                     <ns1:operator>EQUALS</ns1:operator>
                     <ns1:values>100</ns1:values>
                  </ns1:filters>
                  <ns1:filters>
                     <ns1:field>imps</ns1:field>
                     <ns1:operator>IN</ns1:operator>
                     <ns1:values>100,200,300,400</ns1:values>
                  </ns1:filters>
                  <ns1:segments>CLICK_TYPE</ns1:segments>
                  <ns1:fields>cpc</ns1:fields>
                  <ns1:fields>imps</ns1:fields>
                  <ns1:fields>pv</ns1:fields>
                  <ns1:format>XML</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:zip>ON</ns1:zip>
                  <ns1:lang>JA</ns1:lang>
                  <ns1:frequency>SPECIFYDAY</ns1:frequency>
                  <ns1:specifyDay>1</ns1:specifyDay>
                  <ns1:addTemplate>NO</ns1:addTemplate>
               </ns1:reportDefinition>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>11522</ns1:reportId>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderIds>10</ns1:feedFolderIds>
                  <ns1:feedFolderIds>11</ns1:feedFolderIds>
                  <ns1:reportName>Sample AD_CUSTOMIZERS Report</ns1:reportName>
                  <ns1:reportType>AD_CUSTOMIZERS</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20150401</ns1:startDate>
                     <ns1:endDate>20150630</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:segments>CONVERSIONNAME</ns1:segments>
                  <ns1:segments>DAY</ns1:segments>
                  <ns1:segments>DAYOFWEEK</ns1:segments>
                  <ns1:segments>DEVICE</ns1:segments>
                  <ns1:segments>MONTH</ns1:segments>
                  <ns1:segments>MONTHOFYEAR</ns1:segments>
                  <ns1:segments>NETWORK</ns1:segments>
                  <ns1:segments>OBJECTIVEOFCONVERSIONTRACKING</ns1:segments>
                  <ns1:segments>QUARTER</ns1:segments>
                  <ns1:segments>WEEK</ns1:segments>
                  <ns1:segments>YEAR</ns1:segments>
                  <ns1:sort>+FEEDID</ns1:sort>
                  <ns1:fields>ADGROUPID</ns1:fields>
                  <ns1:fields>ADGROUPNAME</ns1:fields>
                  <ns1:fields>ADID</ns1:fields>
                  <ns1:fields>ADNAME</ns1:fields>
                  <ns1:fields>AVERAGECPC</ns1:fields>
                  <ns1:fields>AVERAGECPM</ns1:fields>
                  <ns1:fields>AVERAGEPOSITION</ns1:fields>
                  <ns1:fields>CAMPAIGNID</ns1:fields>
                  <ns1:fields>CAMPAIGNNAME</ns1:fields>
                  <ns1:fields>CLICKS</ns1:fields>
                  <ns1:fields>COST</ns1:fields>
                  <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>CTR</ns1:fields>
                  <ns1:fields>EDITORIALSTATUS</ns1:fields>
                  <ns1:fields>FEEDID</ns1:fields>
                  <ns1:fields>FEEDITEMATTRIBUTES</ns1:fields>
                  <ns1:fields>FEEDITEMENDDATE</ns1:fields>
                  <ns1:fields>FEEDITEMID</ns1:fields>
                  <ns1:fields>FEEDITEMSTARTDATE</ns1:fields>
                  <ns1:fields>IMPRESSIONS</ns1:fields>
                  <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALREVENUE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
                  <ns1:format>CSV</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:zip>OFF</ns1:zip>
                  <ns1:lang>EN</ns1:lang>
                  <ns1:frequency>SPECIFYDAY</ns1:frequency>
                  <ns1:specifyDay>28</ns1:specifyDay>
                  <ns1:addTemplate>YES</ns1:addTemplate>
               </ns1:reportDefinition>
           </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReportFields
### Request
Returns the available report fields for a given report type.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| accountId | Req | xsd:long | Account ID | 
|reportType | Req | [enum ReportType](../data/enum ReportType.md) | Type of report. |
| lang |  | [enum ReportLang](../data/enum ReportLang.md) | Specify language for report field. <br>If omit, EN will be specified. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope　xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
         <ns1:accountId>10000000001</ns1:accountId>
         <ns1:reportType>FEED_ITEM</ns1:reportType>
         <ns1:lang>EN</ns1:lang>
      </ns1:getReportFields>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionFieldValue](../data/ReportDefinitionFieldValue.md) | The list of available report fields. | 

##### Response Sample [AD chosen in reportType]
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>ReportDefinitionService</ns1:service>
         <ns1:remainingQuota>4999</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>2.2749</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getReportFieldsResponse>
         <ns1:rval>
            <ns1:operationSucceeded>true</ns1:operationSucceeded>
            <ns1:field>
               <ns1:fieldName>COST</ns1:fieldName>
               <ns1:displayFieldName>Cost</ns1:displayFieldName>
               <ns1:xmlAttributeName>cost</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>IMPRESSIONS</ns1:fieldName>
               <ns1:displayFieldName>Impressions</ns1:displayFieldName>
               <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CLICKS</ns1:fieldName>
               <ns1:displayFieldName>Clicks</ns1:displayFieldName>
               <ns1:xmlAttributeName>clicks</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CTR</ns1:fieldName>
               <ns1:displayFieldName>CTR</ns1:displayFieldName>
               <ns1:xmlAttributeName>ctr</ns1:xmlAttributeName>
               <ns1:fieldType>Double</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVERAGECPM</ns1:fieldName>
               <ns1:displayFieldName>Avg. CPM</ns1:displayFieldName>
               <ns1:xmlAttributeName>averageCpm</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVERAGECPC</ns1:fieldName>
               <ns1:displayFieldName>Avg. CPC</ns1:displayFieldName>
               <ns1:xmlAttributeName>averageCpc</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVERAGEPOSITION</ns1:fieldName>
               <ns1:displayFieldName>Avg. Position</ns1:displayFieldName>
               <ns1:xmlAttributeName>averagePosition</ns1:xmlAttributeName>
               <ns1:fieldType>Double</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>TOTALREVENUE</ns1:fieldName>
               <ns1:displayFieldName>Total Revenue</ns1:displayFieldName>
               <ns1:xmlAttributeName>totalRevenue</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>UNIQUECONVERSIONS</ns1:fieldName>
               <ns1:displayFieldName>Unique Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>uniqueConversions</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>UNIQUECONVERSIONRATE</ns1:fieldName>
               <ns1:displayFieldName>Unique Conversion Rate</ns1:displayFieldName>
               <ns1:xmlAttributeName>uniqueConversionRate</ns1:xmlAttributeName>
               <ns1:fieldType>Double</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>REVENUEUNIQUECONVERSIONS</ns1:fieldName>
               <ns1:displayFieldName>Revenue / Unique Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>revenueUniqueConversions</ns1:xmlAttributeName>
               <ns1:fieldType>Double</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>REVENUETOTALCONVERSIONS</ns1:fieldName>
               <ns1:displayFieldName>Revenue / Total Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>revenueTotalConversions</ns1:xmlAttributeName>
               <ns1:fieldType>Double</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>TOTALCONVERSIONS</ns1:fieldName>
               <ns1:displayFieldName>Total Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>totalConversions</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>TOTALCONVERSIONRATE</ns1:fieldName>
               <ns1:displayFieldName>Total Conversion Rate</ns1:displayFieldName>
               <ns1:xmlAttributeName>totalConversionRate</ns1:xmlAttributeName>
               <ns1:fieldType>Double</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>COSTUNIQUECONVERSIONS</ns1:fieldName>
               <ns1:displayFieldName>Cost / Unique Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>costUniqueConversions</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>COSTTOTALCONVERSIONS</ns1:fieldName>
               <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CAMPAIGNID</ns1:fieldName>
               <ns1:displayFieldName>CampaignID</ns1:displayFieldName>
               <ns1:xmlAttributeName>campaignID</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>ADGROUPID</ns1:fieldName>
               <ns1:displayFieldName>Ad Group ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>adgroupID</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>ADID</ns1:fieldName>
               <ns1:displayFieldName>Ad ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>adID</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CAMPAIGNNAME</ns1:fieldName>
               <ns1:displayFieldName>Campaign Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>campaignName</ns1:xmlAttributeName>
               <ns1:fieldType>String</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>ADGROUPNAME</ns1:fieldName>
               <ns1:displayFieldName>Ad Group Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>adgroupName</ns1:xmlAttributeName>
               <ns1:fieldType>String</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>ADNAME</ns1:fieldName>
               <ns1:displayFieldName>Ad Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>adName</ns1:xmlAttributeName>
               <ns1:fieldType>String</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>EDITORIALSTATUS</ns1:fieldName>
               <ns1:displayFieldName>Editorial Status</ns1:displayFieldName>
               <ns1:xmlAttributeName>editorialStatus</ns1:xmlAttributeName>
               <ns1:fieldType>Enum</ns1:fieldType>
               <ns1:enumValues>APPROVED</ns1:enumValues>
               <ns1:enumValues>APPROVED_WITH_REVIEW</ns1:enumValues>
               <ns1:enumValues>REVIEW</ns1:enumValues>
               <ns1:enumValues>PRE_DISAPPROVED</ns1:enumValues>
               <ns1:enumValues>POST_DISAPPROVED</ns1:enumValues>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>FEEDITEMID</ns1:fieldName>
               <ns1:displayFieldName>Ad Display Option ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>adDisplayOptionID</ns1:xmlAttributeName>
               <ns1:fieldType>Long</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>PLACEHOLDERTYPE</ns1:fieldName>
               <ns1:displayFieldName>Ad Display Option Type</ns1:displayFieldName>
               <ns1:xmlAttributeName>adDisplayOptionType</ns1:xmlAttributeName>
               <ns1:fieldType>Enum</ns1:fieldType>
               <ns1:enumValues>SITELINKS</ns1:enumValues>
               <ns1:enumValues>CALL</ns1:enumValues>
               <ns1:enumValues>APP</ns1:enumValues>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>QUICKLINKTEXT</ns1:fieldName>
               <ns1:displayFieldName>QuickLink Text</ns1:displayFieldName>
               <ns1:xmlAttributeName>quickLinkText</ns1:xmlAttributeName>
               <ns1:fieldType>String</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>QUICKLINKURL</ns1:fieldName>
               <ns1:displayFieldName>QuickLink URL</ns1:displayFieldName>
               <ns1:xmlAttributeName>quickLinkURL</ns1:xmlAttributeName>
               <ns1:fieldType>String</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>PHONENUMBER</ns1:fieldName>
               <ns1:displayFieldName>Phone Number</ns1:displayFieldName>
               <ns1:xmlAttributeName>phoneNumber</ns1:xmlAttributeName>
               <ns1:fieldType>String</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>DEVICEPREFERENCE</ns1:fieldName>
               <ns1:displayFieldName>Focus Device</ns1:displayFieldName>
               <ns1:xmlAttributeName>focusDevice</ns1:xmlAttributeName>
               <ns1:fieldType>String</ns1:fieldType>
               <ns1:enumValues>__EMPTY__</ns1:enumValues>
               <ns1:enumValues>SMART_PHONE</ns1:enumValues>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
            </ns1:field>
         </ns1:rval>
      </ns1:getReportFieldsResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
### Request
Adds report definitions.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operation | Req | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | A list of unique operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:feedFolderIds>10</ns1:feedFolderIds>
               <ns1:feedFolderIds>11</ns1:feedFolderIds>
               <ns1:reportName>Sample AD_CUSTOMIZERS Report　</ns1:reportName>
               <ns1:reportType>AD_CUSTOMIZERS</ns1:reportType>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20150401</ns1:startDate>
                  <ns1:endDate>20150630</ns1:endDate>
               </ns1:dateRange>
               <ns1:segments>CONVERSIONNAME</ns1:segments>
               <ns1:segments>DAY</ns1:segments>
               <ns1:segments>DAYOFWEEK</ns1:segments>
               <ns1:segments>DEVICE</ns1:segments>
               <ns1:segments>MONTH</ns1:segments>
               <ns1:segments>MONTHOFYEAR</ns1:segments>
               <ns1:segments>NETWORK</ns1:segments>
               <ns1:segments>OBJECTIVEOFCONVERSIONTRACKING　</ns1:segments>
               <ns1:segments>QUARTER</ns1:segments>
               <ns1:segments>WEEK</ns1:segments>
               <ns1:segments>YEAR</ns1:segments>
               <ns1:sort>+FEEDID</ns1:sort>
               <ns1:fields>ADGROUPID</ns1:fields>
               <ns1:fields>ADGROUPNAME</ns1:fields>
               <ns1:fields>ADID</ns1:fields>
               <ns1:fields>ADNAME</ns1:fields>
               <ns1:fields>AVERAGECPC</ns1:fields>
               <ns1:fields>AVERAGECPM</ns1:fields>
               <ns1:fields>AVERAGEPOSITION</ns1:fields>
               <ns1:fields>CAMPAIGNID</ns1:fields>
               <ns1:fields>CAMPAIGNNAME</ns1:fields>
               <ns1:fields>CLICKS</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
               <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
               <ns1:fields>CTR</ns1:fields>
               <ns1:fields>EDITORIALSTATUS</ns1:fields>
               <ns1:fields>FEEDID</ns1:fields>
               <ns1:fields>FEEDITEMATTRIBUTES</ns1:fields>
               <ns1:fields>FEEDITEMENDDATE</ns1:fields>
               <ns1:fields>FEEDITEMID</ns1:fields>
               <ns1:fields>FEEDITEMSTARTDATE</ns1:fields>
               <ns1:fields>IMPRESSIONS</ns1:fields>
               <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
               <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
               <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
               <ns1:fields>TOTALCONVERSIONS</ns1:fields>
               <ns1:fields>TOTALREVENUE</ns1:fields>
               <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
               <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>OFF</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:frequency>SPECIFYDAY</ns1:frequency>
               <ns1:specifyDay>28</ns1:specifyDay>
               <ns1:addTemplate>YES</ns1:addTemplate>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container for report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
            <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturn　Value.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>11522</ns1:reportId>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderIds>10</ns1:feedFolderIds>
                  <ns1:feedFolderIds>11</ns1:feedFolderIds>
                  <ns1:reportName>Sample AD_CUSTOMIZERS Report　</ns1:reportName>
                  <ns1:reportType>AD_CUSTOMIZERS</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20150401</ns1:startDate>
                     <ns1:endDate>20150630</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:segments>CONVERSIONNAME</ns1:segments>
                  <ns1:segments>DAY</ns1:segments>
                  <ns1:segments>DAYOFWEEK</ns1:segments>
                  <ns1:segments>DEVICE</ns1:segments>
                  <ns1:segments>MONTH</ns1:segments>
                  <ns1:segments>MONTHOFYEAR</ns1:segments>
                  <ns1:segments>NETWORK</ns1:segments>
                  <ns1:segments>OBJECTIVEOFCONVERSIONTRACKING　</ns1:segments>
                  <ns1:segments>QUARTER</ns1:segments>
                  <ns1:segments>WEEK</ns1:segments>
                  <ns1:segments>YEAR</ns1:segments>
                  <ns1:sort>+FEEDID</ns1:sort>
                  <ns1:fields>ADGROUPID</ns1:fields>
                  <ns1:fields>ADGROUPNAME</ns1:fields>
                  <ns1:fields>ADID</ns1:fields>
                  <ns1:fields>ADNAME</ns1:fields>
                  <ns1:fields>AVERAGECPC</ns1:fields>
                  <ns1:fields>AVERAGECPM</ns1:fields>
                  <ns1:fields>AVERAGEPOSITION</ns1:fields>
                  <ns1:fields>CAMPAIGNID</ns1:fields>
                  <ns1:fields>CAMPAIGNNAME</ns1:fields>
                  <ns1:fields>CLICKS</ns1:fields>
                  <ns1:fields>COST</ns1:fields>
                  <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>CTR</ns1:fields>
                  <ns1:fields>EDITORIALSTATUS</ns1:fields>
                  <ns1:fields>FEEDID</ns1:fields>
                  <ns1:fields>FEEDITEMATTRIBUTES</ns1:fields>
                  <ns1:fields>FEEDITEMENDDATE</ns1:fields>
                  <ns1:fields>FEEDITEMID</ns1:fields>
                  <ns1:fields>FEEDITEMSTARTDATE</ns1:fields>
                  <ns1:fields>IMPRESSIONS</ns1:fields>
                  <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALREVENUE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
                  <ns1:format>CSV</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:zip>OFF</ns1:zip>
                  <ns1:lang>EN</ns1:lang>
                  <ns1:frequency>SPECIFYDAY</ns1:frequency>
                  <ns1:specifyDay>28</ns1:specifyDay>
                  <ns1:addTemplate>YES</ns1:addTemplate>
               </ns1:reportDefinition>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
### Request
Updates report definitions.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operation | Req | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | A list of unique operations. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
       <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
              <ns1:reportId>11522</ns1:reportId>
               <ns1:accountId>100000001</ns1:accountId>
                <ns1:reportName>Sample AD_CUSTOMIZERS Report Modify</ns1:reportName>
              <ns1:frequency>SPECIFYDAY</ns1:frequency>
               <ns1:specifyDay>10</ns1:specifyDay>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container for report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>11522</ns1:reportId>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:feedFolderIds>10</ns1:feedFolderIds>
                  <ns1:feedFolderIds>11</ns1:feedFolderIds>
                  <ns1:reportName>Sample AD_CUSTOMIZERS Report Modify</ns1:reportName>
                  <ns1:reportType>AD_CUSTOMIZERS</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20150401</ns1:startDate>
                     <ns1:endDate>20150630</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:segments>CONVERSIONNAME</ns1:segments>
                  <ns1:segments>DAY</ns1:segments>
                  <ns1:segments>DAYOFWEEK</ns1:segments>
                  <ns1:segments>DEVICE</ns1:segments>
                  <ns1:segments>MONTH</ns1:segments>
                  <ns1:segments>MONTHOFYEAR</ns1:segments>
                  <ns1:segments>NETWORK</ns1:segments>
                  <ns1:segments>OBJECTIVEOFCONVERSIONTRACKING</ns1:segments>
                  <ns1:segments>QUARTER</ns1:segments>
                  <ns1:segments>WEEK</ns1:segments>
                  <ns1:segments>YEAR</ns1:segments>
                  <ns1:sort>+FEEDID</ns1:sort>
                  <ns1:fields>ADGROUPID</ns1:fields>
                  <ns1:fields>ADGROUPNAME</ns1:fields>
                  <ns1:fields>ADID</ns1:fields>
                  <ns1:fields>ADNAME</ns1:fields>
                  <ns1:fields>AVERAGECPC</ns1:fields>
                  <ns1:fields>AVERAGECPM</ns1:fields>
                  <ns1:fields>AVERAGEPOSITION</ns1:fields>
                  <ns1:fields>CAMPAIGNID</ns1:fields>
                  <ns1:fields>CAMPAIGNNAME</ns1:fields>
                  <ns1:fields>CLICKS</ns1:fields>
                  <ns1:fields>COST</ns1:fields>
                  <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>CTR</ns1:fields>
                  <ns1:fields>EDITORIALSTATUS</ns1:fields>
                  <ns1:fields>FEEDID</ns1:fields>
                  <ns1:fields>FEEDITEMATTRIBUTES</ns1:fields>
                  <ns1:fields>FEEDITEMENDDATE</ns1:fields>
                  <ns1:fields>FEEDITEMID</ns1:fields>
                  <ns1:fields>FEEDITEMSTARTDATE</ns1:fields>
                  <ns1:fields>IMPRESSIONS</ns1:fields>
                  <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALREVENUE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
                  <ns1:format>CSV</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:zip>OFF</ns1:zip>
                  <ns1:lang>EN</ns1:lang>
                  <ns1:frequency>SPECIFYDAY</ns1:frequency>
                  <ns1:specifyDay>10</ns1:specifyDay>
                  <ns1:addTemplate>YES</ns1:addTemplate>
               </ns1:reportDefinition>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
### Request
Deletes report definitions.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operation | Req | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | A list of unique operations. | 

##### Request Sample
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
### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| operations | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container for report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:ListReturnValue.Type>ReportDefinitionReturnValue　</ns1:ListReturnValue.Type>
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
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
