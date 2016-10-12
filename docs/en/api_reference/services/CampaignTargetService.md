# CampaignTargetService
CampaignTargetService is to get or update target setting information.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/CampaignTargetService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/CampaignTargetService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### Overview
Get, add, update or delete campaign informations related to targeting setting.<br>
* Bid Adjustment (bidmultiplier) is only modifiable for each targeting.<br>
* The available operations vary depending on the target. Please refer to the chart below for details.<br>
* Cannot mutate(SET) for Network Targeting. For the change, delete first using mutate(REMOVE), then create the new target using mutate(ADD).

| Target | mutate(ADD) | mutate(SET) | mutate(REMOVE) | Notes |
|---|---|---|---|---|
| Day of Week / Hours targeting | OK | OK | OK | |
| Geo targeting | OK | OK | OK | |
| Device targeting | NG | OK | NG | New registration and deletion of Device Targeting is not available.<br>Device Targeting which is automatically registered at the time of campaign new creation is only modifiable (bidMultiplier will be set “1”). |
| Network targeting | OK | NG | OK | Registration of "bidmultiplier" is not available. |

#### Operation
Describes the operation which provides at CampaignTargetService.
## get
### Request
Gets campaign informations related to targeting setting.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [CampaignTargetSelector](../data/CampaignTargetSelector.md) | Operation elements for targeting setting of campaign. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>9999-9999-9999-9999</ns1:license>
         <ns1:apiAccountId>8888-8888-8888-8888</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>14201</ns1:accountId>
            <ns1:campaignIds>7261</ns1:campaignIds>
            <ns1:campaignIds>7262</ns1:campaignIds>
            <ns1:campaignIds>7263</ns1:campaignIds>
            <ns1:targetIds>JP011112222</ns1:targetIds>
            <ns1:targetIds>011112222</ns1:targetIds>
            <ns1:targetIds>911112222</ns1:targetIds>
            <ns1:targetTypes>SCHEDULE</ns1:targetTypes>
            <ns1:targetTypes>LOCATION</ns1:targetTypes>
            <ns1:targetTypes>PLATFORM</ns1:targetTypes>
            <ns1:targetTypes>NETWORK</ns1:targetTypes>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>500</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```
### Response
Response Field

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [CampaignTargetPage](../data/CampaignTargetPage.md) | Page of lists of the requested campaign targets. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>14201</ns1:accountId>
                        <ns1:campaignId>7261</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetId>011112222</ns1:targetId>
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>14201</ns1:accountId>
                     <ns1:campaignId>7261</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>              
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>14201</ns1:accountId>
                        <ns1:campaignId>7262</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetId>811112222</ns1:targetId>
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>14201</ns1:accountId>
                        <ns1:campaignId>7262</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:PlatformTarget">
                            <ns1:targetId>811112222</ns1:targetId>
                            <ns1:targetType>PLATFORM</ns1:targetType>
                            <ns1:platformType>SMART_PHONE</ns1:platformType>
                        </ns1:target>
                        <ns1:bidMultiplier>3.0</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>14201</ns1:accountId>
                        <ns1:campaignId>7262</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:PlatformTarget">
                            <ns1:targetId>811112223</ns1:targetId>
                            <ns1:targetType>PLATFORM</ns1:targetType>
                            <ns1:platformType>TABLET</ns1:platformType>
                        </ns1:target>
                        <ns1:bidMultiplier>2.0</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>14201</ns1:accountId>
                        <ns1:campaignId>7262</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:PlatformTarget">
                            <ns1:targetId>811112223</ns1:targetId>
                            <ns1:targetType>PLATFORM</ns1:targetType>
                            <ns1:platformType>DESKTOP</ns1:platformType>
                        </ns1:target>
                        <ns1:bidMultiplier>0</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
### Request
Adds campaign informations related to targeting setting.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignTargetOperation](../data/CampaignTargetOperation.md) | Operation elements for targeting setting of campaign | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns1="http://ss.yahooapis.jp/V6" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:ScheduleTarget">
                  <ns1:targetType>SCHEDULE</ns1:targetType>
                  <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                  <ns1:startHour>21</ns1:startHour>
                  <ns1:startMinute>ZERO</ns1:startMinute>
                  <ns1:endHour>24</ns1:endHour>
                  <ns1:endMinute>ZERO</ns1:endMinute>
               </ns1:target>
               <ns1:bidMultiplier>1</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:LocationTarget">
                  <ns1:targetId>JP-0001-0010</ns1:targetId>
                  <ns1:targetType>LOCATION</ns1:targetType>
                  <ns1:excludedType>INCLUDED</ns1:excludedType>
               </ns1:target>
               <ns1:bidMultiplier>1</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000004</ns1:campaignId>
               <ns1:target xsi:type="ns1:PlatformTarget">
                  <ns1:targetType>PLATFORM</ns1:targetType>
                  <ns1:platformType>SMART_PHONE</ns1:platformType>
               </ns1:target>
               <ns1:bidMultiplier>1</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000005</ns1:campaignId>
               <ns1:target xsi:type="ns1:NetworkTarget">
                  <ns1:targetType>NETWORK</ns1:targetType>
                  <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
               </ns1:target>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
### Response
Response Fields

| Field | Requirement | Data Type | 
|---|---|---|
| rval | [CampaignTargetReturnValue](../data/CampaignTargetReturnValue.md) | Page of lists of the requested campaign targets. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetId>011112222</ns1:targetId>
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>00000001</ns1:accountId>
                     <ns1:campaignId>00000003</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000004</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetId>811112222</ns1:targetId>
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate (SET)
### Request
Update campaign informations related to targeting setting.
* Bid Adjustment (bidmultiplier) is only modifiable.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignTargetOperation](../data/CampaignTargetOperation.md) | Operation elements for targeting setting of campaign. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns1="http://ss.yahooapis.jp/V6" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000006</ns1:campaignId>
               <ns1:target xsi:type="ns1:ScheduleTarget">
                  <ns1:targetId>00124534</ns1:targetId>
                  <ns1:targetType>SCHEDULE</ns1:targetType>
               </ns1:target>
               <ns1:bidMultiplier>1.5</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000006</ns1:campaignId>
               <ns1:target xsi:type="ns1:LocationTarget">
                  <ns1:targetId>JP-0001-0010</ns1:targetId>
                  <ns1:targetType>LOCATION</ns1:targetType>
               </ns1:target>
               <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000006</ns1:campaignId>
               <ns1:target xsi:type="ns1:PlatformTarget">
                  <ns1:targetId>0124534</ns1:targetId>
                  <ns1:targetType>PLATFORM</ns1:targetType>
               </ns1:target>
               <ns1:bidMultiplier>3</ns1:bidMultiplier>
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
| rval | [CampaignTargetReturnValue](../data/CampaignTargetReturnValue.md) | Page of lists of the requested campaign targets. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetId>011112222</ns1:targetId>
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>00000001</ns1:accountId>
                     <ns1:campaignId>00000003</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000004</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetId>811112222</ns1:targetId>
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate (REMOVE)
### Request
Delete campaign informations related to targeting setting.

| Field | Restrictions | Data Type | Description | 
|---|---|---|---|
| operations | Req | [CampaignTargetOperation](../data/CampaignTargetOperation.md) | Operation elements for targeting setting of campaign. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope 
xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" 
xmlns:ns1="http://ss.yahooapis.jp/V6" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>REMOVE</ns1:operator>
            <ns1:accountId>00000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:ScheduleTarget">
                  <ns1:targetId>011112222</ns1:targetId>
                  <ns1:targetType>SCHEDULE</ns1:targetType>
               </ns1:target>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:LocationTarget">
                  <ns1:targetId>JP-0001-0010</ns1:targetId>
                  <ns1:targetType>LOCATION</ns1:targetType>
               </ns1:target>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>00000001</ns1:accountId>
               <ns1:campaignId>00000003</ns1:campaignId>
               <ns1:target xsi:type="ns1:NetworkTarget">
                  <ns1:targetId>811112222</ns1:targetId>
                  <ns1:targetType>NETWORK</ns1:targetType>
               </ns1:target>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </soapenv:Body>
</soapenv:Envelope>
```
### Response
##### Response Fields

| Field | Requirement | Data Type | 
|---|---|---|
| rval | [CampaignTargetReturnValue](../data/CampaignTargetReturnValue.md) | Page of lists of the requested campaign targets. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>CampaignTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>CampaignTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
               <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000003</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:ScheduleTarget">
                           <ns1:targetId>011112222</ns1:targetId>
                           <ns1:targetType>SCHEDULE</ns1:targetType>
                           <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                           <ns1:startHour>21</ns1:startHour>
                           <ns1:startMinute>ZERO</ns1:startMinute>
                           <ns1:endHour>24</ns1:endHour>
                           <ns1:endMinute>ZERO</ns1:endMinute>
                        </ns1:target>
                        <ns1:bidMultiplier>1</ns1:bidMultiplier>
                    </ns1:campaignTarget>
                </ns1:values>
                 <ns1:values>
                  <ns1:operationSucceeded>true</ns1:operationSucceeded>
                  <ns1:campaignTarget>
                     <ns1:accountId>00000001</ns1:accountId>
                     <ns1:campaignId>00000003</ns1:campaignId>
                     <ns1:campaignName>Sample2</ns1:campaignName>
                     <ns1:target xsi:type="ns1:LocationTarget">
                     <ns1:targetId>JP-0001-0010</ns1:targetId>
                        <ns1:targetType>LOCATION</ns1:targetType>
                        <ns1:provinceNameJA>東京都</ns1:provinceNameJA>
                        <ns1:provinceNameEN>Tokyo</ns1:provinceNameEN>
                        <ns1:cityNameJA>港区</ns1:cityNameJA>
                        <ns1:cityNameEN>Minatoku</ns1:cityNameEN>
                        <ns1:excludedType>INCLUDED</ns1:excludedType>
                        <ns1:targetingStatus>ACTIVE</ns1:targetingStatus>
                     </ns1:target>
                     <ns1:bidMultiplier>0.95</ns1:bidMultiplier>
                  </ns1:campaignTarget>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:campaignTarget>
                        <ns1:accountId>00000001</ns1:accountId>
                        <ns1:campaignId>00000004</ns1:campaignId>
                        <ns1:campaignName>Sample</ns1:campaignName>
                        <ns1:target xsi:type="ns1:NetworkTarget">
                            <ns1:targetId>811112222</ns1:targetId>
                            <ns1:targetType>NETWORK</ns1:targetType>
                            <ns1:networkCoverageType>YAHOO_SEARCH</ns1:networkCoverageType>
                        </ns1:target>
                    </ns1:campaignTarget>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
