# Sponsored Search Report
## What is “Performance Report”?
Performance Report is a function of confirming performance in Campaign, Ad Group, Ad, Keyword, etc.   
To display report, creation of report and template will be required.    
Customizing report is possible, like setting hierarchy of performance, item display, summary period, etc.  
  
Report functions supported in Campaign management Tool are also available from API.  
## How to operate from Sponsored Search API
To display the performance report, use the two services below from Sponsored Search API.  
##### 1.	ReportDefinitionService   
ReportDefinitionService can retrieve and add/update/delete the report definition.   
Report definition will designate the report type, period or field.  
##### 2.	ReportService  
ReportService can retrieve and add/delete the report.  
It also can retrieve the Download URL of report.  
## Scenerio Sample
This is a process of create and delete of report template and actual report, to retrieve Performance Report, using Sponsored Search API.  
#### 1.	Retrieve Field of Template
Use getReportFields of ReportDefinitionService.  
Retrieve list of available report fields by designated ReportType.  
Each report fields encapsulate the field name, field data type, and enumerations.
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:getReportFields>
         <ns1:accountId>10000000001</ns1:accountId>
         <ns1:reportType>AD</ns1:reportType>
         <ns1:lang>EN</ns1:lang>
      </ns1:getReportFields>
   </soapenv:Body>
</soapenv:Envelope>
```
##### Response Sample
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
#### 2.	Create Report Template
Use mutat:add of ReportDefinitionService.  
Creates the report template.
It requires the following:  
* Name of report definition
* Designating the type of PERFORMANCE_REPORT
* Designating segment
* Designating summary period
* Designating creation time (Frequency)
* Japanese/English selection
* Designating output format

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>100000001</ns1:accountId>
               <ns1:campaignIds>4322</ns1:campaignIds>
               <ns1:adGroupIds>1850001</ns1:adGroupIds>
               <ns1:kwIds>1000000</ns1:kwIds>
               <ns1:adIds>1830001</ns1:adIds>
               <ns1:feedItemIds>1241</ns1:feedItemIds>
               <ns1:reportName>Sample FEED_ITEM Report</ns1:reportName>
               <ns1:reportType>FEED_ITEM</ns1:reportType>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20121201</ns1:startDate>
                  <ns1:endDate>20130110</ns1:endDate>
               </ns1:dateRange>
              <ns1:sort>+QUICKLINKTEXT</ns1:sort>
               <ns1:fields>PLACEHOLDERTYPE</ns1:fields>
               <ns1:fields>QUICKLINKTEXT</ns1:fields>
               <ns1:fields>QUICKLINKURL</ns1:fields>
               <ns1:fields>PHONENUMBER</ns1:fields>
               <ns1:fields>IMPRESSIONS</ns1:fields>
               <ns1:fields>CLICKS</ns1:fields>
               <ns1:fields>CTR</ns1:fields>
               <ns1:fields>AVERAGEPOSITION</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>AVERAGECPC</ns1:fields>
               <ns1:fields>FEEDITEMID</ns1:fields>
               <ns1:fields>DEVICEPREFERENCE</ns1:fields>
               <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
               <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
               <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
               <ns1:fields>AVERAGECPM</ns1:fields>
               <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
               <ns1:fields>TOTALREVENUE</ns1:fields>
               <ns1:fields>TOTALCONVERSIONS</ns1:fields>
               <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
               <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
               <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
               <ns1:fields>CAMPAIGNNAME</ns1:fields>
               <ns1:fields>CAMPAIGNID</ns1:fields>
               <ns1:fields>ADGROUPNAME</ns1:fields>
               <ns1:fields>ADGROUPID</ns1:fields>
               <ns1:fields>ADNAME</ns1:fields>
               <ns1:fields>ADID</ns1:fields>
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
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>11522</ns1:reportId>
                  <ns1:accountId>100000001</ns1:accountId>
                  <ns1:campaignIds>4322</ns1:campaignIds>
                  <ns1:adGroupIds>1850001</ns1:adGroupIds>
                  <ns1:kwIds>1000000</ns1:kwIds>
                  <ns1:adIds>1830001</ns1:adIds>
                  <ns1:feedItemIds>1241</ns1:feedItemIds>
                  <ns1:reportName>Sample FEED_ITEM Report</ns1:reportName>
                  <ns1:reportType>FEED_ITEM</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20121201</ns1:startDate>
                     <ns1:endDate>20130110</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:sort>+QUICKLINKTEXT</ns1:sort>
                  <ns1:fields>PLACEHOLDERTYPE</ns1:fields>
                  <ns1:fields>QUICKLINKTEXT</ns1:fields>
                  <ns1:fields>QUICKLINKURL</ns1:fields>
                  <ns1:fields>PHONENUMBER</ns1:fields>
                  <ns1:fields>IMPRESSIONS</ns1:fields>
                  <ns1:fields>CLICKS</ns1:fields>
                  <ns1:fields>CTR</ns1:fields>
                  <ns1:fields>AVERAGEPOSITION</ns1:fields>
                  <ns1:fields>COST</ns1:fields>
                  <ns1:fields>AVERAGECPC</ns1:fields>
                  <ns1:fields>FEEDITEMID</ns1:fields>
                  <ns1:fields>DEVICEPREFERENCE</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>COSTUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>UNIQUECONVERSIONRATE</ns1:fields>
                  <ns1:fields>AVERAGECPM</ns1:fields>
                  <ns1:fields>REVENUEUNIQUECONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALREVENUE</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                  <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>REVENUETOTALCONVERSIONS</ns1:fields>
                  <ns1:fields>CAMPAIGNNAME</ns1:fields>
                  <ns1:fields>CAMPAIGNID</ns1:fields>
                  <ns1:fields>ADGROUPNAME</ns1:fields>
                  <ns1:fields>ADGROUPID</ns1:fields>
                  <ns1:fields>ADNAME</ns1:fields>
                  <ns1:fields>ADID</ns1:fields>
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
#### 3.	Create Report
Use mutate:add of ReportServiceのmutate:add.  
Creates report from designated ReportID.
*This process is not necessary for Scheduled Report.  
##### Request Sample
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
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>IN_PROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>IN_PROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 4.	Confirm the Report Status
Use get of ReportService.  
Can confirm the report creation status.  
##### Request Sample
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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:reportIds>100000003</ns1:reportIds>
                <ns1:reportIds>100000007</ns1:reportIds>
                <ns1:reportIds>100000005</ns1:reportIds>
                <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
                <ns1:reportJobStatuses>INPROGRESS</ns1:reportJobStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
  
or
  
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:reportJobIds>100000003</ns1:reportJobIds>
                <ns1:reportJobIds>100000007</ns1:reportJobIds>
                <ns1:reportJobIds>100000005</ns1:reportJobIds>
                <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
                <ns1:reportJobStatuses>INPROGRESS</ns1:reportJobStatuses>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
                <ns1:Page.Type>ReportPage</ns1:Page.Type>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>IN_PROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>IN_PROGRESS</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 5.	Download Report
Uses getDownloadUrl of ReportService.  
Retrieves report files by designating accountID and/or reportJobID.  
##### Request Sample
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
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getDownloadUrl>
            <ns1:selector>
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:reportJobIds>100000003</ns1:reportJobIds>
                <ns1:reportJobIds>100000007</ns1:reportJobIds>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>10</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:getDownloadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getDownloadUrlResponse>
            <ns1:rval>
                <ns1:Page.Type>ReportDownloadUrlPage</ns1:Page.Type>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDownloadUrl>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>IN_PROGRESS</ns1:status>
                        <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/UEX3InsUoShWXa3YcX3AmbObSahcIylBoDZS5ftx7qS4VtqxGco6BpBFnJF3CRAGM5jSHqs77QZqm2P2jvKe3Dy7</ns1:downloadUrl>
                    </ns1:reportDownloadUrl>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDownloadUrl>
                        <ns1:accountId>10000000001</ns1:accountId>
                        <ns1:reportJobId>200000001</ns1:reportJobId>
                        <ns1:reportId>10000000001</ns1:reportId>
                        <ns1:reportName>test</ns1:reportName>
                        <ns1:requestTime>20110630232230</ns1:requestTime>
                        <ns1:completeTime>20110701062230</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                             <ns1:startDate>20110301</ns1:startDate>
                             <ns1:endDate>20111011</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>IN_PROGRESS</ns1:status>
                        <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/3CRAGObSahcIylBoDZS5ftx7qS4VM5jSHqs77QZqmpBFnJFP2jvKe3Dy72UEX3InsUoShWXa3YcX3AmbtqxGco6B</ns1:downloadUrl>
                    </ns1:reportDownloadUrl>
                </ns1:values>
            </ns1:rval>
        </ns1:getDownloadUrlResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 6.	Delete Report
Use mutate:remove of ReportService.  
Deletes downloaded report from ReportList.  
##### Request Sample
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V5">
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
#### 7.	Delete Report Template
Uses mutate:remove of ReportDefinitionService.  
Deletes the unnecessary defined report.  
##### Request Sample
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
                    <ns1:reportId>10000000001</ns1:reportId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
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
